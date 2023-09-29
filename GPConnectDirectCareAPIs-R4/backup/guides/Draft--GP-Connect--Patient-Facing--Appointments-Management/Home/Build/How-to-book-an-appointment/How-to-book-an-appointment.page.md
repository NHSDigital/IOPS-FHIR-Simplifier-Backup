---
topic: how-to-book-an-appointment
---

## {{page-title}}

## Use case ##

<div class="alert alert-info nhsd-t-body" role="alert">
<i class="fa fa-info-circle"></i> <b>Note:</b> This API is aimed at the administration of a patient's appointments. As a result of information governance (IG) requirements, the book appointment capability has been restricted to future appointments. See {{pagelink:design-principles}}.
</div>

The typical flow to book an appointment is:

 1. Search by NHS Number for, or otherwise obtain, a Patient resource.
 2. Search for available `Slot` resources by date range.
 3. Create an `Appointment` for the chosen `Slot` and created `Patient` resources.

See {{pagelink:Home/Design/Interactions/Appointment-consumer-sessions.page.md}} for how this use case could be used in the context of a typical consumer appointment management session.

## Security ##

GP Connect utilises a JSON Web Tokens (JWT) to transmit clinical audit and provenance detail.

## Prerequisites ##

### Consumer ###

The consumer system:

- **SHALL** have previously resolved the organisation's FHIR&reg; endpoint base URL through the [endpoint lookup process]()
- **SHALL** have received the patient's NHS number from the client app
- **SHALL** have previously obtained the details for one or more free slots that are to be booked, using {{pagelink:how-to-search-for-free-slots}}

## Consumer display requirements ##

Consumer systems **SHALL** support the following fields to provide the full context of the appointment in the current IM1 standard: 

- confirmation of appointment booking outcome (success, failure, and so on)

## API usage ##

The consumer system **SHALL** only use the book appointment capability to book future appointments, where the appointment start dateTime is after the current date and time. If the appointment start date is in the past the provider **SHALL** return an error.

Adherence is expected to local business rules, agreements and policies defining good practice in GP Connect-enabled cross-organisational appointment booking. This will discourage, for example, the over-booking and subsequent cancellation of slots.

### Booking multiple adjacent slots ###

To book more than one slot in the same Book Appointment message, a consumer needs to be able to identify which adjacent slots may be booked together.  This is determined by the following rules:
  - two slots (Slot A and Slot B) are adjacent when the start time of Slot B equals the end time of Slot A
  - the adjacent slots **SHALL** reference the same `Schedule` resource
  - the adjacent slots **SHALL** both have the same `deliveryChannel` value
  - the adjacent slots **SHALL** both have the same `serviceType` value
  - if the slots do not conform to one or more of the rules above, they **SHALL NOT** be accepted as part of the same appointment booking

### Request operation ###

#### FHIR relative request ####

```http
POST /Appointment
```

#### FHIR absolute request ####

```http
POST https://[proxy_server]/https://[provider_server]/[fhir_base]/Appointment
```

#### Payload request body ####

The request payload is a profiled version of the standard FHIR [Appointment](https://www.hl7.org/fhir/STU3/appointment.html) resource. See {{pagelink:Home/FHIR-Assets/All-Assets}} for more detail.

Consumer systems:
- **SHALL** send an `Appointment` resource that conforms to the {{pagelink:Home/FHIR-Assets/All-Assets/Profiles/Profile--GPConnect-Appointment-1}} profile
- **SHALL** include the URI of the `GPConnect-Appointment-1` profile StructureDefinition in the `Appointment.meta.profile` element of the appointment resource

The following data elements are mandatory (that is, data **MUST** be present):

- a patient `participant` of the appointment with `Patient.telecom.system`, `Patient.telecom.value`, `Patient.telecom.use` field populated if the appointment is a telephone appointment 
- an `actor` reference in any supplied `participant`
- the `start` and `end` of the appointment
  - where multiple slots are being booked, the `start` **SHALL** be the start time of the earlier slot, and the `end` **SHALL** be the end time of the latest slot
- the `status` identifying the appointment as 'booked'
- the `slot` details of one or more free slots to be booked
  - where multiple slots are being booked, they **SHALL** meet the conditions required to be booked together - see {{pagelink:how-to-book-an-appointment}}

- the bookingOrganisation extension referencing a contained Organization resource within the appointment resource
  - the contained organization resource **SHALL** represent the organization booking the appointment
  - the contained organization resource **SHALL** conform to CareConnect-GPC-Organization-1 profile
  - the contained organization resource **SHALL** contain an identifier with the organisation’s ODS code
  - the contained organization resource **SHALL** contain at least name and telecom details
  - the contained organization resource **SHALL** include the type element with a value matching the organization type sent as a searchFilter with the Search for free slots request - if organization type was not passed to the searchFilter then type **SHALL** not be populated

- the `created` element **SHALL** be populated with the date and time the appointment was created

- `reason` element with the patient's reason for booking

### Request response ###

#### Response headers ####

Provider systems are not expected to add any specific headers beyond that described in the HTTP and FHIR&reg; standards.

#### Payload response body ####

Provider systems:

- **SHALL** return a `201` **Created** HTTP status code on successful execution of the operation
- **SHALL** return a `Location` header as described in {{pagelink:Home/Build/FHIR-API-guidance.page.md}}
- **SHALL** return an `Appointment` resource that conforms to the {{pagelink:Home/FHIR-Assets/All-Assets/Profiles/Profile--GPConnect-Appointment-1}} profile
- **SHALL** include the URI of the `GPConnect-Appointment-1` profile StructureDefinition in the `Appointment.meta.profile` element of the returned appointment resource
- **SHALL** include the `versionId` of the current version of each appointment resource
- **SHALL** populate `Appointment.serviceType.text` with the practice-defined slot type description, and where available `Appointment.serviceCategory.text` with a practice-defined schedule type description (may be called session name or rota type)

- **SHALL** meet {{pagelink:Home/Build/FHIR-Resource-Guidance.page.md}} populating all fields where data is available, excluding those listed below

- **SHALL NOT** populate the following fields:
  - `specialty`
  - `reason`

#### Error handling ####

Provider systems:

- **SHALL** return an HTTP status "409" with an error message "DUPLICATE_REJECTED" when an appointment cannot be booked because the referenced slots within the appointment resource no longer have the status `free`, such as when the slot has been used to book a different appointment between the "search for free slots" request and the "book appointment" request
- **SHALL** return an error if `specialty` is included in the appointment resource sent by the consumer
- **SHALL** return a {{pagelink:Home/FHIR-Assets/All-Assets/Profiles/Profile--GPConnect-OperationOutcome-1}} resource that provides additional detail when one or more request fields are corrupt or a specific business rule/constraint is breached

For example:

- the submitted `start` and `end` date range does not match that of the requested slot(s)
- one or more of the requested `Slot` resources does not exist or already has a `status` of busy
- a business rule imposed by {{pagelink:how-to-search-for-free-slots}} is breached, such as an organisational slot limit
- multiple slots were requested for booking but do not meet the criteria for {{pagelink:how-to-book-an-appointment}}
- the `description` or `comment` fields contain more characters than can be stored in the provider system

Refer to {{pagelink:error-handling}} for details of error codes.

<div class="alert alert-info nhsd-t-body" role="alert">
<i class="fa fa-info-circle"></i> <b>Note:</b> Provider systems <b>MAY</b> implement business rules to protect the responsible use of the booking API, in line with current business rules already in place, to prevent misuse of appointment booking outside of implementation.
</div>

## Examples ##

### Book an appointment ###

#### Request ####

The consumer system constructs an `Appointment` resource from slot (and its associated schedule) chosen by the user and posts the resource to the `/Appointment` endpoint to book the appointment. The consumer organisation making the booking is populated as a contained resource.

```http
POST /Appointment
```

```json
{
  "resourceType": "Appointment",
  "meta": {
    "profile": [
      "https://fhir.nhs.uk/STU3/StructureDefinition/GPConnect-Appointment-1"
    ]
  },
    "contained": [
    {
      "resourceType": "Organization",
      "id": "1",
      "meta": {
        "profile": [
          "https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Organization-1"
        ]
      },
      "identifier": [
        {
          "system": "https://fhir.nhs.uk/Id/ods-organization-code",
          "value": "A00001"
        }
      ],
      "type": [
        {
          "coding": [
            {
              "system": "https://fhir.nhs.uk/STU3/CodeSystem/GPConnect-OrganisationType-1",
              "code": "gp-practice"
            }
          ]
        }
      ],
      "name": "Test Organization Name",
      "telecom": [
        {
          "system": "phone",
          "value": "0300 303 5678"
        }
      ]
    }
  ],
  "extension": [
    {
      "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-GPConnect-BookingOrganisation-1",
      "valueReference": {
        "reference": "#1"
      }
    }
  ],
  "status": "booked",
   "reason": [
          {
            "text": "tennis elbow"
          }
        ],
  "description": "Free text description.",
  "start": "2017-05-30T10:00:00+01:00",
  "end": "2017-05-30T10:25:00+01:00",
  "slot": [
       "resource": {
        "resourceType": "Slot",
        "id": "1584",
        "meta": {
          "versionId": "1471219260000",
          "profile": [
            "https://fhir.nhs.uk/STU3/StructureDefinition/GPConnect-Slot-1"
          ]
        },
        "extension": [
          {
            "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-GPConnect-DeliveryChannel-2",
            "valueCode": "In-person"
          }
        ],
        "serviceType": [
          {
            "text": "GP Appointment"
          }
        ],
        "schedule": {
          "reference": "Schedule/14"
        },
        "status": "free",
        "start": "2017-09-15T11:30:00+01:00",
        "end": "2017-09-15T11:40:00+01:00"
      }
  ],
  "created": "2017-05-25T13:48:41+01:00",
  "comment": "Free text comment.",
  "participant": [
    {
      "actor": {
        "reference": "Patient/1"
      },
      "status": "accepted"
    }
  ]
}
```

#### Response ####

The provider system responds back with the Appointment resource with the `id` field populated to indicate the appointment was booked.

```json
{
  "resourceType": "Appointment",
  "id": "9",
  "meta": {
    "versionId": "636068818095315079",
    "profile": [
      "https://fhir.nhs.uk/STU3/StructureDefinition/GPConnect-Appointment-1"
    ]
  },
  "contained": [
    {
      "resourceType": "Organization",
      "id": "1",
      "meta": {
        "profile": [
          "https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Organization-1"
        ]
      },
      "identifier": [
        {
          "system": "https://fhir.nhs.uk/Id/ods-organization-code",
          "value": "Z100"
        }
      ],
      "type": [
        {
          "coding": [
            {
              "system": "https://fhir.nhs.uk/STU3/CodeSystem/GPConnect-OrganisationType-1",
              "code": "urgent-care"
            }
          ]
        }
      ],
      "name": "North Ambulance Service",
      "telecom": [
        {
          "system": "phone",
          "value": "01111222333"
        }
      ]
    }
  ],
  "extension": [
    {
      "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-GPConnect-BookingOrganisation-1",
      "valueReference": {
        "reference": "#1"
      }
    },
    {
      "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-GPConnect-PractitionerRole-1",
      "valueCodeableConcept": {
        "coding": [
          {
            "system": "https://fhir.nhs.uk/STU3/CodeSystem/CareConnect-SDSJobRoleName-1",
            "code": "R0260",
            "display": "General Medical Practitioner"
          }
        ]
      }
    },
    {
      "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-GPConnect-DeliveryChannel-2",
      "valueCode": "In-person"
    }
  ],
  "status": "booked",
  "serviceCategory": {
    "text": "General GP Appointments"
  },
  "serviceType": [
    {
      "text": "General GP Appointment"
    }
  ],
  "description": "Free text description.",
  "start": "2017-05-30T10:00:00+01:00",
  "end": "2017-05-30T10:25:00+01:00",
  "minutesDuration": 25,
  "slot": [
    {
      "reference": "Slot/1"
    }
  ],
  "created": "2017-05-25T13:48:41+01:00",
  "comment": "Free text comment.",
  "participant": [
    {
      "actor": {
        "reference": "Patient/1"
      },
      "status": "accepted"
    },
    {
      "actor": {
        "reference": "Location/32"
      },
      "status": "accepted"
    }
  ]
}
```
---