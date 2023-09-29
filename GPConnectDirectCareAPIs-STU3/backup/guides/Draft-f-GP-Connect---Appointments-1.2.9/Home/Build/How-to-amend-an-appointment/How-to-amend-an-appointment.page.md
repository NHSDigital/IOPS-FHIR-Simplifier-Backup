## {{page-title}}

## Use case ##

This API is used to amend the `description` or `comment` fields of a patient's future appointment, obtained via either the [Retrieve a patient's appointments](https://simplifier.net/guide/PFS-Appointments/Home/Build/How-to-retrieve-a-patients-appointments?version=current), or [Read an appointment](https://simplifier.net/guide/PFS-Appointments/Home/Build/How-to-read-an-appointment?version=current) APIs.

Any future appointment irrespective of booking organisation, and irrespective of whether the appointment was booked via the GP Connect API, can be amended by a consuming organisation participating with the appointment hosting organisation in a GP Connect deployment.

The typical flow to amend an appointment is:

 1. Search by NHS number for, or otherwise obtain, a `Patient` resource.
 2. Search for `Appointment` resources for the `Patient` resource.
 3. Choose an `Appointment` resource and update `description` and/or `comment` fields.

Amending a cancelled appointment is NOT supported.

<div markdown="span" class="alert alert-info" role="alert"><i class="fa fa-info-circle"></i> <b>Note:</b>The Appointment Management capability pack is aimed at administration of a patient's appointments. As a result of information governance (IG) requirements, the amend appointments capability has been restricted to future appointments. More details are available on the <a href=https://simplifier.net/guide/PFS-Appointments/Home/Design/Design-Principals.page.md?version=current> Design principals </a> page.</div>

## Security ##

- GP Connect utilises TLS Mutual Authentication for system level authorization
- GP Connect utilises a JSON Web Tokens (JWT) to transmit clinical audit and provenance details 

## Prerequisites ##

### Consumer ###

The consumer system:

- SHALL have previously resolved the organisation's FHIR endpoint base URL through the [Spine Directory Service](https://developer.nhs.uk/apis/gpconnect-1-2-7/integration_spine_directory_service.html)
- SHALL have previously traced the patient's NHS Number using the [Personal Demographics Service]( https://developer.nhs.uk/apis/gpconnect-1-2-7/integration_personal_demographic_service.html) or an equivalent service
- SHALL have previously found the appointment ID using [Retrieve a patient's appointments](https://simplifier.net/guide/PFS-Appointments/Home/Build/How-to-retrieve-a-patients-appointments?version=current)

## API usage ##

The consumer system SHALL only use the amend appointment capability to amend:

  - `description` or `comment` fields.  Providers SHALL return an error when any other field is amended.
  - future appointments where appointment start date/time is after the current date/time. If the appointment start date/time is in the past the provider SHALL return an error.
  - appointments that have not been cancelled.  Providers SHALL return an error where an amendment to a cancelled appointment is received.

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

Consumers SHALL include the following additional HTTP request headers:

| Header               | Value |
|----------------------|-------|
| `Ssp-TraceID`        | Consumer's TraceID (i.e. GUID/UUID) |
| `Ssp-From`           | Consumer's ASID |
| `Ssp-To`             | Provider's ASID |
| `Ssp-InteractionID`  | `urn:nhs:names:services:gpconnect:fhir:rest:update:appointment-1` |
| `If-Match`           | The Appointment's current [ETag](https://developer.nhs.uk/apis/gpconnect-1-2-7/development_general_api_guidance.html#managing-resource-contention#managing-resource-contention), e.g. `W/"23"` |

#### Payload request body ####

The request payload is a profiled version of the standard FHIR [Appointment](https://www.hl7.org/fhir/STU3/appointment.html) resource. See [FHIR resources](/datalibraryappointment.html) page for more detail.

Consumer systems:
- SHALL send an `Appointment` resource that conforms to the [GPConnect-Appointment-1](https://fhir.nhs.uk/STU3/StructureDefinition/GPConnect-Appointment-1) profile.
- SHALL include the URI of the `GPConnect-Appointment-1` profile StructureDefinition in the `Appointment.meta.profile` element of the appointment resource.
- SHALL NOT amend an appointment with a status of `cancelled`

Only the following data elements can be modified when performing an appointment amendment:
- `description` containing a brief description of the appointment.
  - Consumers SHALL impose a character limit of 100 characters for this element.
  - This element SHALL only contain limited information to support the appointment and SHALL NOT be used for "transfer of care" clinical information.
- `comment` containing 'patient specific notes' and any additional comments relating to the appointment.
  - Consumers SHALL impose a character limit of 500 characters for this element.
  - This element SHALL only contain limited information to support the appointment and SHALL NOT be used for "transfer of care" clinical information.

<div markdown="span" class="alert alert-info" role="alert"><i class="fa fa-info-circle"></i> <b>Note:</b>It is recommended that Consumers read the Appointment they wish to amend (via Read an appointment or Retrieve a patient's appointments), then update the fields allowed below in place. Attempting to recreate the Appointment resource from local transformed data formats/structures is not advised, and may result in the provider system rejecting the amendment due to an unintended change or missing field. </div>

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

- SHALL return a `200` **OK** HTTP status code on successful execution of the operation.
- SHALL return an `Appointment` resource that conforms to the [GPConnect-Appointment-1](https://simplifier.net/guide/PFS-Appointments/Home/FHIR-Assets/All-Assets/Profiles/Profile--GPConnect-Appointment-1?version=current) profile.
- SHALL include the URI of the `GPConnect-Appointment-1` profile StructureDefinition in the `Appointment.meta.profile` element of the returned appointment resource.
- SHALL include the `versionId` of the current version of the appointment resource.

- SHALL populate `serviceType.text` with the practice defined slot type description, and where available `serviceCategory.text` with a practice defined schedule type description (may be called session name or rota type).

- SHALL meet [General FHIR resource population requirements](https://simplifier.net/guide/PFS-Appointments/Home/Build/FHIR-Resources.page.md?version=current#general-fhir-resource-population-requirements) populating all fields where data is available, excluding those listed below

- SHALL NOT populate the following fields:
  - `reason`
  - `specialty`

#### Error handling ####

The provider system:

- SHALL return a [GPConnect-OperationOutcome-1](https://simplifier.net/guide/PFS-Appointments/Home/FHIR-Assets/All-Assets/Profiles/Profile--GPConnect-OperationOutcome-1?version=current) resource that provides additional detail when one or more request fields are corrupt or a specific business rule/constraint is breached.
- SHALL return an error where:
  - any appointment details other than the appointment `comment` or `description` are amended. The appointment resource should be considered invalid and the provider system should return a `422` error with error code `INVALID_RESOURCE`.
  - the appointment being amended is in the past (the appointment start dateTime is before the current date and time).
  - the appointment has been cancelled.  Provider systems should return a `422` error with error code `INVALID_RESOURCE`.
  - the version identifier in the `If-Match` header does not match the Appointment's current version identifier.  See [Managing resource contention](https://simplifier.net/guide/PFS-Appointments/Home/Build/FHIR-Resources.page.md?version=current#managing-resource-contention).
  - the `description` or `comment` fields contain more characters than can be stored in the provider system

Refer to [Development - FHIR API guidance - error handling](https://simplifier.net/guide/PFS-Appointments/Home/Build/Error-Handling.page.md?version=current) for details of error codes.

## Examples ##

### Amend an appointment ###

#### Request ####

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
          "value": "03003035678"
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
    },
    {
      "actor": {
        "reference": "Practitioner/18"
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
    "versionId": "6360688180953112345",
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
          "value": "03003035678"
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
    },
    {
      "actor": {
        "reference": "Practitioner/18"
      },
      "status": "accepted"
    }
  ]
}
```
---