## {{page-title}}

## Use case ##

This specification describes a single use case enabling the consumer to obtain the details of a specific future appointment from a targeted provider system.

A patient's future appointment, irrespective of the booking organisation, and irrespective of whether the appointment was booked via the GP Connect API, is  returned by the provider system.

<div markdown="span" class="alert alert-info" role="alert"><i class="fa fa-info-circle"></i> <b>Note:</b>The Appointment Management capability pack is aimed at the administration of a patient's appointments. As a result of information governance (IG) requirements, the read appointments capability has been restricted to future appointments. More details are available on the <a href=https://simplifier.net/guide/pfs-appointments/home-design-design-principals?version=current#viewing-and-amending-booked-appointments>  Design decisions </a> page.</div>


## Security ##

- GP Connect utilises TLS Mutual Authentication for system level authorization
- GP Connect utilises a JSON Web Tokens (JWT) to transmit clinical audit and provenance details

## Prerequisites ##

### Consumer ###

The consumer system:

- SHALL have previously resolved the organisation's FHIR endpoint base URL through the [Spine Directory Service](https://developer.nhs.uk/apis/gpconnect-1-2-7/integration_spine_directory_service.html)

## API usage ##

The consumer system SHALL only use the read appointment capability to retrieve future appointments, where the appointment start dateTime is after the current date and time. If the appointment start date is in the past the provider SHALL return an error.


### Request operation ###

#### FHIR relative request ####

```http
GET /Appointment/[id]
```

#### FHIR absolute request ####

```http
GET https://[proxy_server]/https://[provider_server]/[fhir_base]/Appointment/[id]
```

#### Request headers ####

Consumers SHALL include the following additional HTTP request headers:

| Header               | Value |
|----------------------|-------|
| `Ssp-TraceID`        | Consumer's TraceID (i.e. GUID/UUID) |
| `Ssp-From`           | Consumer's ASID |
| `Ssp-To`             | Provider's ASID |
| `Ssp-InteractionID`  | `urn:nhs:names:services:gpconnect:fhir:rest:read:appointment-1`|

#### Payload request body ####

N/A

### Request response ###

#### Response headers ####

Provider systems are not expected to add any specific headers beyond that described in the HTTP and FHIR&reg; standards.

#### Payload response body ####

Provider systems:

- SHALL return a `200` **OK** HTTP status code on successful execution of the operation.
- SHALL return `Appointment` resources that conform to the [GPConnect-Appointment-1](https://simplifier.net/guide/PFS-Appointments/Home/FHIR-Assets/All-Assets/Profiles/Profile--GPConnect-Appointment-1?version=current) resource profile.
- SHALL include the URI of the `GPConnect-Appointment-1` profile StructureDefinition in the `Appointment.meta.profile` element of the returned appointment resource.
- SHALL include the `versionId` of the current version of the appointment resource.
- SHALL include all relevant business `identifier` details (if any) for the appointment resource.

- SHALL populate `Appointment.start`, `Appointment.end`, `Appointment.created` elements in (UK) local time in the format `yyyy-mm-ddThh:mm:ss+hh:mm`, with the timezone offset `+00:00` for UTC and `+01:00` for BST

- SHALL populate `Appointment.serviceType.text` with the practice defined slot type description, and where available `Appointment.serviceCategory.text` with a practice defined schedule type description (may be called session name or rota type).

- SHALL meet [General FHIR resource population requirements](https://simplifier.net/guide/pfs-appointments/home-build-fhir-resource-guidance?version=current#general-fhir-resource-population-requirements) populating all fields where data is available, excluding those listed below

- SHALL NOT populate the following fields:
  - `reason`
  - `specialty`

#### Error handling ####

Provider systems:
- SHALL return an [GPConnect-OperationOutcome-1](https://simplifier.net/guide/PFS-Appointments/Home/FHIR-Assets/All-Assets/Profiles/Profile--GPConnect-OperationOutcome-1?version=current) resource that provides additional detail when one or more data fields are corrupt or a specific business rule/constraint is breached.
- SHALL return an error if the appointment being read is in the past (the appointment start dateTime is before the current date and time).

Examples of other scenarios which may result in error being returned:
- Where a logical identifier of the resource is not valid/can't be found on the server, a 404 HTTP Status code would be returned with the relevant OperationOutcome resource.
- Where insufficient data about an appointment is present in the provider system to populate an appointment resource which validates to the `GPConnect-Appointment-1` profile, a 500 HTTP Status code should be returned, together with the appropriate OperationOutcome resource providing diagnostic detail.

Refer to [Development - FHIR API Guidance - Error Handling](https://simplifier.net/guide/pfs-appointments/guides-pfs-appointments-home-build-error-handling?version=current) for details of error codes.

## Examples ##

### Read an appointment by id ###

#### Request ####

```http
GET /Appointment/150
```

#### Response ####

```json
{
  "resourceType": "Appointment",
  "id": "150",
  "meta": {
    "versionId": "1503440820000",
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
  "description": "GP Connect Appointment description 148",
  "start": "2017-08-17T11:20:00+01:00",
  "end": "2017-08-17T11:30:00+01:00",
  "slot": [
    {
      "reference": "Slot/303"
    }
  ],
  "created": "2017-08-14T13:48:41+01:00",
  "participant": [
    {
      "actor": {
        "reference": "Patient/1001"
      },
      "status": "accepted"
    },
    {
      "actor": {
        "reference": "Location/1"
      },
      "status": "accepted"
    }
  ]
}
```
---