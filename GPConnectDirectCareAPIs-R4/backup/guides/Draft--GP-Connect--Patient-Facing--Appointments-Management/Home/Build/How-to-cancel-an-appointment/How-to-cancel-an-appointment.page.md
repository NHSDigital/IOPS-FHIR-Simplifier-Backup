---
topic: how-to-cancel-an-appointment
---

## {{page-title}}

## Use case ##

This API is used to cancel a patient's future appointment, obtained through either {{pagelink:how-to-retrieve-a-patients-appointments}} or {{pagelink:how-to-read-an-appointment}}.

Any future appointment, irrespective of booking organisation or whether the appointment was booked via this API, can be cancelled by a consuming organisation participating with the appointment hosting organisation in a GP Connect deployment.

The typical flow to cancel an appointment is:

 1. Search by NHS Number for, or otherwise obtain, a Patient resource.
 2. Search for `Appointment` resources for the `Patient` resource.
 3. Choose an `Appointment` resource and cancel it by amending the `status` to `cancelled`.

<div class="alert alert-info nhsd-t-body" role="alert">
<i class="fa fa-info-circle"></i> <b>Note:</b> This API is aimed at the administration of a patient's appointments. As a result of information governance (IG) requirements, the book appointment capability has been restricted to future appointments. See {{pagelink:design-principles}}.
</div>

## Security ## 

GP Connect utilises a JSON Web Tokens (JWT) to transmit clinical audit and provenance detail.

## Prerequisites ##

### Consumer ###

The consumer system:

- **SHALL** have previously resolved the organisation's FHIR&reg; endpoint base URL through the [endpoint lookup process]()
- **SHALL** have received the patient's NHS number from the client app
- **SHALL** have previously found the appointment ID using {{pagelink:how-to-retrieve-a-patients-appointments}}
- **SHALL** have populated or otherwise retrieved a patient resource

## Consumer display requirements ##

Consumer systems **SHALL** support the following fields in order to provide the full context of the appointment in the current IM1 standard: 

- confirmation of cancellation of appointment outcome (success, failure, and so on)

## API usage ##

The consumer system **SHALL** only use the cancel appointment capability to cancel future appointments where appointment start dateTime is after the current date and time. If the appointment start date is in the past the provider **SHALL** return an error.

### Request operation ###

#### FHIR relative request ####

```http
PUT /Appointment/[id]
```

#### FHIR absolute request ####

```http
PUT https://[proxy_server]/https://[provider_server]/[fhir_base]/Appointment/[id]
```

#### Request headers ####

Consumers **SHALL** include the following additional HTTP request headers:

| `If-Match`           | The Appointment's current [ETag](./General-API-guidance.page.md?version=current#managing-resource-contention), e.g. `W/"23"` |

#### Payload request body ####

The request payload is a profiled version of the standard FHIR&reg; [Appointment](https://www.hl7.org/fhir/STU3/appointment.html) resource. See {{pagelink:Home/FHIR-Assets/All-Assets}} for more details.

Consumer systems:
- **SHALL** send an `Appointment` resource that conforms to the {{pagelink:Home/FHIR-Assets/All-Assets/Profiles/Profile--GPConnect-Appointment-1}} profile.
- **SHALL** include the URI of the `GPConnect-Appointment-1` profile StructureDefinition in the `Appointment.meta.profile` element of the appointment resource

<div class="alert alert-info nhsd-t-body" role="alert">
<i class="fa fa-info-circle"></i> <b>Note:</b> It is recommended that consumers read the appointment they wish to cancel (via Read an appointment or Retrieve a patient's appointments), then update the fields allowed below in place. Attempting to recreate the Appointment resource from local transformed data formats/structures is not advised, and may result in the provider system rejecting the amendment due to an unintended change or missing field.
</div>

Only the following data elements can be modified when performing an appointment cancellation:
- the appointment `status` **SHALL** be updated to "cancelled"
- the appointment `cancellation-reason` extension **SHALL** be included with the cancellation reason details

<div class="alert alert-info nhsd-t-body" role="alert">
<i class="fa fa-info-circle"></i> <b>Note:</b> If any content other than the appointment cancellation reason or appointment status is updated the server <b>SHALL</b> reject the amendment and return an error.
</div>

<div class="alert alert-info nhsd-t-body" role="alert">
<i class="fa fa-info-circle"></i> <b>Note:</b> GP Connect does not impose a character limit on the cancellation reason extension within the cancellation request, but due to differences in the provider system the cancellation reason may be truncated when stored in the provider system due to character limits.
</div>

### Request response ###

#### Response headers ####

Provider systems are not expected to add any specific headers beyond that described in the HTTP and FHIR&reg; standards.

#### Payload response body ####

Provider systems:

- **SHALL** return a `200` **OK** HTTP status code on successful execution of the operation
- **SHALL** return an `Appointment` resource that conforms to the {{pagelink:Home/FHIR-Assets/All-Assets/Profiles/Profile--GPConnect-Appointment-1}} profile
- **SHALL** include the URI of the `GPConnect-Appointment-1` profile StructureDefinition in the `Appointment.meta.profile` element of the returned appointment resource
- **SHALL** include the `versionId` of the current version of each appointment resource
- **SHALL** have updated the appointment `status` to "cancelled"
- **SHALL** have updated the appointment `cancellation-reason` in line with any details supplied in the request

- **SHALL** populate `serviceType.text` with the practice-defined slot type description, and where available `serviceCategory.text` with a practice-defined schedule type description (may be called session name or rota type)

- **MAY** populate `Appointment.reason.text` with the free text reason for the appointment, if it is populated

- **SHALL** meet {{pagelink:fhir-resource-guidance}} populating all fields where data is available, excluding those listed below

- **SHALL NOT** populate the following fields:
  - `specialty`
  - `reason`

<div class="alert alert-info nhsd-t-body" role="alert">
<i class="fa fa-info-circle"></i> <b>Note:</b> A status response `200` <b>OK</b> implies that the state of any resources affected by the appointment cancellation (for example, the associated `Slot`) subsequently reflects the cancellation (for example, `Appointment.status`, `Slot.status` are updated in line with any internal integrity constraints). 
</div>

#### Error handling ####

The provider system:

- **SHALL** return a {{pagelink:Home/FHIR-Assets/All-Assets/Profiles/Profile--GPConnect-OperationOutcome-1}} resource that provides additional details when one or more data fields are corrupt or a specific business rule/constraint is breached
- **SHALL** return an error if any appointment details other than the appointment `status` and `cancellation-reason` fields are attempted to be updated
- **SHALL** return an error if the appointment being cancelled is in the past (the appointment start dateTime is before the current date and time)
- **SHALL** return an error if the version identifier in the `If-Match` header does not match the appointment's current version identifier see {{pagelink:general-api-guidance}}

See {{pagelink:error-handling}} for details of error codes.

## Examples ##

### Cancel an appointment ###

#### Request ####

The Appointment resource is submitted with the `status` field set to `cancelled` and a FHIR extension carrying the reason for cancellation.

```http
PUT /Appointment/9
```

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
      "name": "West Road GP Practice",
      "telecom": [
        {
          "system": "phone",
          "value": "0300303 5678"
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
      "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-GPConnect-AppointmentCancellationReason-1",
      "valueString": "Free text cancellation reason."
    }
  ],
  "status": "cancelled",
  "description": "Free text description updated.",
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
      "name": "West Road GP Practice",
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
    },
    {
      "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-GPConnect-AppointmentCancellationReason-1",
      "valueString": "Free text cancellation reason."
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
  "status": "cancelled",
  "serviceCategory": {
    "text": "General GP Appointments"
  },
  "serviceType": [
    {
      "text": "General GP Appointment"
    }
  ],
  "description": "Free text description updated.",
  "start": "2017-05-30T10:00:00+01:00",
  "end": "2017-05-30T10:25:00+01:00",
  "minutesDuration": 10,
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