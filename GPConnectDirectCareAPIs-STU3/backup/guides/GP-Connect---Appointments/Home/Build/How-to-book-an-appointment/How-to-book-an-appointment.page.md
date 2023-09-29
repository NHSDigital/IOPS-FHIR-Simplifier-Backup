## {{page-title}}

## Use case ##

<div markdown="span" class="alert alert-info" role="alert"><i class="fa fa-info-circle"></i> <b>Note:</b>The Appointment Management capability pack is aimed at administration of a patient's appointments. As a result of information governance (IG) requirements the book appointment capability has been restricted to future appointments. See <a href =https://simplifier.net/guide/PFS-Appointments/Home/Design/Design-Principals.page.md?version=current#viewing-and-amending-booked-appointments> Design decisions.</a></div>

The typical flow to book an appointment is:

 1. Search by `NHS Number` for, or otherwise obtain, a `Patient` resource.
 2. Search for available `Slot` resources by date range.
 3. Create an `Appointment` for the chosen `Slot` and `Patient` resources.

Refer to [Consumer sessions illustrated](https://simplifier.net/guide/PFS-Appointments/Home/Design/Appointments-Consumer-Sessions.page.md?version=current) for how this API use case could be used in the context of a typical consumer appointment management session.

## Security ##

- GP Connect utilises TLS Mutual Authentication for system level authorization
- GP Connect utilises a JSON Web Tokens (JWT) to transmit clinical audit and provenance details 

## Prerequisites ##

### Consumer ###

The consumer system:

- SHALL have previously resolved the organisation's FHIR&reg; endpoint base URL through the [Spine Directory Service](https://developer.nhs.uk/apis/gpconnect-1-2-7/integration_spine_directory_service.html)
- SHALL have previously traced the patient's NHS Number using the [Personal Demographics Service]( https://developer.nhs.uk/apis/gpconnect-1-2-7/integration_personal_demographic_service.html) or an equivalent service.
- SHALL have previously obtained the details for one or more free slots that are to be booked, using [Search for free slots](https://simplifier.net/guide/PFS-Appointments/Home/Build/How-to-search-for-free-slots?version=current)
- SHALL have previously performed a [Find a patient](https://developer.nhs.uk/apis/gpconnect-1-2-7/foundations_use_case_find_a_patient.html) request to obtain the logical identifier for the patient on the organisation's FHIR server.

## API usage ##

The consumer system SHALL only use the book appointment capability to book future appointments, where the appointment start dateTime is after the current date and time. If the appointment start date is in the past the provider SHALL return an error.

Adherence is expected to local business rules, agreements and policies defining good practice in GP Connect-enabled cross-organisational appointment booking.  This will discourage for example the over-booking and subsequent cancellation of Slots.

### Booking multiple adjacent slots ###

To book more than one slot in the same Book Appointment message, a consumer needs to be able to identify which adjacent slots may be booked together.  This is determined by the following rules:
  - Two slots (Slot A and Slot B) are adjacent when the start time of Slot B equals the end time of Slot A
  - The adjacent slots SHALL reference the same `Schedule` resource
  - The adjacent slots SHALL both have the same `deliveryChannel` value
  - The adjacent slots SHALL both have the same `serviceType` value
  - If the slots do not conform to one or more of the rules above, they SHALL NOT be accepted as part of the same appointment booking

### Request operation ###

#### FHIR relative request ####

```http
POST /Appointment
```

#### FHIR absolute request ####

```http
POST https://[proxy_server]/https://[provider_server]/[fhir_base]/Appointment
```

#### Request headers ####

Consumers SHALL include the following additional HTTP request headers:

| Header               | Value |
|----------------------|-------|
| `Ssp-TraceID`        | Consumer's TraceID (i.e. GUID/UUID) |
| `Ssp-From`           | Consumer's ASID |
| `Ssp-To`             | Provider's ASID |
| `Ssp-InteractionID`  | `urn:nhs:names:services:gpconnect:fhir:rest:create:appointment-1` |


#### Payload request body ####

The request payload is a profiled version of the standard FHIR [Appointment](https://www.hl7.org/fhir/STU3/appointment.html) resource. See the [FHIR resources](/datalibraryappointment.html) page for more detail.

Consumer systems:
- SHALL send an `Appointment` resource that conforms to the [GPConnect-Appointment-1](https://simplifier.net/guide/PFS-Appointments/Home/FHIR-Assets/All-Assets/Profiles/Profile--GPConnect-Appointment-1?version=current) profile.
- SHALL include the URI of the `GPConnect-Appointment-1` profile StructureDefinition in the `Appointment.meta.profile` element of the appointment resource.

The following data elements are mandatory (that is, data **MUST** be present):

- a patient `participant` of the appointment.
- a location `participant` of the appointment, representing the physical location where the appointment is to take place (see [Design decisions](https://developer.nhs.uk/apis/gpconnect-1-2-7/foundations_design.html#location-in-the-appointment-resource) page).
- an `actor` reference in any supplied `participant`.
- the `start` and `end` of the appointment.
  - where multiple slots are being booked, the `start` SHALL be the start time of the earlier slot, and the `end` shall be the end time of the latest slot
- the `status` identifying the appointment as "booked".
- the `slot` details of one or more free slots to be booked.
  - where multiple slots are being booked, they SHALL meet the conditions required to be booked together - see [Booking multiple adjacent slots](https://simplifier.net/guide/PFS-Appointments/Home/Build/How-to-book-an-appointment?version=current#booking-multiple-adjacent-slots)
- the `bookingOrganisation` extension referencing an [contained](https://www.hl7.org/fhir/STU3/references.html#contained) `Organization` resource within the appointment resource.
  - the contained organization resource SHALL represent the organization booking the appointment.
  - the contained organization resource SHALL conform to [CareConnect-GPC-Organization-1](https://simplifier.net/guide/PFS-Appointments/Home/FHIR-Assets/All-Assets/Profiles/Profile--CareConnect-GPC-Organization-1?version=current) profile.
  - the contained organization resource SHALL contain an `identifier` with the organisation's ODS code.
  - the contained organization resource SHALL contain at least `name` and `telecom` details.
  - the contained organization resource SHALL include the `type` element with a value matching the organization type sent as a `searchFilter` with the [Search for free slots](https://simplifier.net/guide/PFS-Appointments/Home/Build/How-to-search-for-free-slots?version=current) request. If organization type was not passed to the `searchFilter` then `type` SHALL not be populated.
- the `created` element SHALL be populated with the date and time the appointment was created.
- `description` containing a brief description of the appointment.
  - Consumers SHALL impose a character limit of 100 characters for this element.
  - This element SHALL only contain limited information to support the appointment and SHALL NOT be used for "transfer of care" clinical information.

The following data elements **SHOULD** be included when available:
- a practitioner `participant` of the appointment.

The following data elements **MAY** be included:

- `comment` containing 'patient specific notes' and any additional comments relating to the appointment.
  - Consumers SHALL impose a character limit of 500 characters for this element.
  - This element SHALL only contain limited information to support the appointment and SHALL NOT be used for "transfer of care" clinical information.

The following data elements **MUST NOT** be included:
  - `reason`
  - `specialty`

<div markdown="span" class="alert alert-info" role="alert"><i class="fa fa-info-circle"></i> <b>Note:</b> The provider system receiving the bookingOrganization details SHALL store, return and display these details as required by the [Must-Support]<a href =https://simplifier.net/guide/PFS-Appointments/Home/Build/FHIR-API-Guidance.page.md?version=current#use-of-must-support-flag> Must-Support </a> flag </div>

#### Provider handling of description and comment ####

When receiving `description` and `comment` fields in the provider system:

- Providers systems SHALL store information received in `description` and `comment` fields, supporting the character limit lengths shown above 
- Providers systems SHALL NOT truncate information received in `description` or `comment` fields
- Providers SHALL return `description` and `comment` fields to the consumer in the response payload, as stored
- Where a consumer sends information longer than character limits supported, an error SHALL be returned to the consumer
- Where there are not two suitable appointment text fields in a provider system, providers MAY concatenate `description` and `comment` (with suitable delimiters) in order to store in a single field, such that data is not lost

### Request response ###

#### Response headers ####

Provider systems are not expected to add any specific headers beyond that described in the HTTP and FHIR&reg; standards.

#### Payload response body ####

Provider systems:

- SHALL return a `201` **Created** HTTP status code on successful execution of the operation.
- SHALL return a `Location` header as described in [FHIR API guidance](https://simplifier.net/guide/PFS-Appointments/Home/Build/FHIR-API-Guidance.page.md?version=current#create-resource).
- SHALL return an `Appointment` resource that conform to the [GPConnect-Appointment-1](https://simplifier.net/guide/PFS-Appointments/Home/FHIR-Assets/All-Assets/Profiles/Profile--GPConnect-Appointment-1?version=current) profile.
- SHALL include the URI of the `GPConnect-Appointment-1` profile StructureDefinition in the `Appointment.meta.profile` element of the returned appointment resource.
- SHALL include the `versionId` of the current version of each appointment resource.
- SHALL populate `Appointment.serviceType.text` with the practice defined slot type description, and where available `Appointment.serviceCategory.text` with a practice defined schedule type description (may be called session name or rota type).

- SHALL meet [General FHIR resource population requirements](https://simplifier.net/guide/pfs-appointments/home-build-fhir-resource-guidance?version=current#general-fhir-resource-population-requirements) populating all fields where data is available, excluding those listed below

- SHALL NOT populate the following fields:
  - `reason`
  - `specialty`

#### Error handling ####

Provider systems:

- SHALL return an HTTP status "409" with an error message "DUPLICATE_REJECTED" when an appointment cannot be booked because the referenced slots within the appointment resource no longer have the status `free`, such as when the slot has been used to book a different appointment between the "search for free slots" request and the "book appointment" request.
- SHALL return an error if `reason` or `specialty` is included in the appointment resource sent by the consumer.
- SHALL return a [GPConnect-OperationOutcome-1](https://simplifier.net/guide/PFS-Appointments/Home/FHIR-Assets/All-Assets/Profiles/Profile--GPConnect-OperationOutcome-1?version=current) resource that provides additional detail when one or more request fields are corrupt or a specific business rule/constraint is breached.

For example:

- the submitted `start` and `end` date range does not match that of the requested slot(s)
- one or more of the requested `Slot` resources does not exist or already has a `status` of busy
- a business rule imposed by [Slot Availability Management](https://simplifier.net/guide/pfs-appointments/home-design-slot-availability-management?version=current) is breached, e.g. an organisational slot limit
- multiple slots were requested for booking but do not meet the criteria for [booking multiple adjacent slots](https://simplifier.net/guide/PFS-Appointments/Home/Build/How-to-book-an-appointment?version=current#booking-multiple-adjacent-slots)
- the `description` or `comment` fields contain more characters than can be stored in the provider system

Refer to [Development - FHIR API guidance - error handling](https://simplifier.net/guide/pfs-appointments/guides-pfs-appointments-home-build-error-handling?version=current) for details of error codes.

<div markdown="span" class="alert alert-info" role="alert"><i class="fa fa-info-circle"></i> <b>Note:</b>Provider systems MAY implement business rules to protect the responsible use of the booking API, in line with current business rules already in place, to prevent misuse of appointment booking outside of the GP Connect API implementation.</div>

## Examples ##

### Book an appointment ###

#### Request ####

The consumer system constructs an `Appointment` resource from slot (and its associated schedule) chosen by the user and posts the resource to the `/Appointment` endpoint in order to book the appointment.  The consumer organisation making the booking is populated as a contained resource.

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
    }
  ],
  "status": "booked",
  "description": "Free text description.",
  "start": "2017-05-30T10:00:00+01:00",
  "end": "2017-05-30T10:25:00+01:00",
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