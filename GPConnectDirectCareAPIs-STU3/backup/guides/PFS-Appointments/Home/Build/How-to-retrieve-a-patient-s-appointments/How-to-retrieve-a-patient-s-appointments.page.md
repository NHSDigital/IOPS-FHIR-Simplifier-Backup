---
topic: how-to-retrieve-a-patients-appointments
---

## {{page-title}}

## Use case ##

This specification describes a single use case enabling the patient to retrieve future appointment bookings from a targeted provider system. 

All future appointments for the patient, irrespective of the booking organisation, and irrespective of whether the appointment was booked via this API, will be returned from the provider system.

## Security ##

GP Connect utilises a JSON Web Tokens (JWT) to transmit clinical audit and provenance detail.

## Prerequisites ##

### Consumer ###

The consumer system:

- **SHALL** have previously resolved the organisation's FHIR&reg; endpoint base URL through the endpoint lookup process
- **SHALL** have received the patient's NHS number from the client app
- **SHALL** have previously [resolved the logical ID of the patient](https://developer.nhs.uk/apis/gpconnect-1-2-7/foundations_use_case_find_a_patient.html) on the server using the NHS number

## Consumer display requirements ##

Consumer systems **SHALL** support the following fields in order to provide the full context of the appointment in the current IM1 standard: 

- start date and time
- slot type and schedule type (see `Appointment.serviceType` and `Appointment.serviceCategory`)
- location name
- practitioner role (for example, General Medical Practitioner, Nurse)
- practitioner name and gender

## API usage ##

### Request operation ###

#### Search parameters ####

Provider systems **SHALL** implement the following search parameters:

| Name | Type | Description | Paths |
| --- | --- | --- | --- |
| `start` | `date` | Appointment start date | `Appointment.start` |


Consumer systems:
- **SHALL** include two `start` search parameter with every request
  - one of the `start` search parameter **SHALL** be supplied with the `ge` search prefix (for example, `start=ge2017-09-22`, which indicates that the consumer would like appointments where the appointment start date is on or after "2017-09-22")
  - one of the `start` search parameter **SHALL** be supplied with the `le` search prefix (for example, `start=le2017-09-25`, which indicates that the consumer would like appointments where the appointment start date is on or before "2017-09-25")
- **SHALL** only include the date component of the search parameter and not a time component - the date **SHALL** include day, month and year elements

Diagram - Date range parameters

{{render:Searchforfreeslotstimeline.png}}

Provider systems:
- **SHALL** support the search prefixes `ge` and `le`
- **SHALL** return an error if either of the date parameters contain a time element
- **SHALL** return an error if either of the two start date parameters are not sent with the consumer's request

#### FHIR relative request ####


```http
GET /Patient/[id]/Appointment?start=ge[lower_date_range_boundary]&start=le[upper_date_range_boundary]
```

#### FHIR absolute request ####

```http
GET https://[proxy_server]/https://[provider_server]/[fhir_base]/Patient/[id]/Appointment?start=ge[lower_date_range_boundary]&start=le[upper_date_range_boundary]
```
#### Payload request body ####

N/A

### Request response ###

#### Response headers ####

Provider systems are not expected to add any specific headers beyond that described in the HTTP and FHIR&reg; standards.

#### Payload response body ####

Provider systems:

- **SHALL** return a `200` **OK** HTTP status code on successful execution of the operation
- **SHALL** return zero or more matching {{pagelink:Home/FHIR-Assets/All-Assets/Profiles/Profile--GPConnect-Appointment-1}} resources in a `Bundle` of `type` searchset
- **SHALL** include the URI of the `GPConnect-Appointment-1` profile StructureDefinition in the `Appointment.meta.profile` element of the returned `Appointment` resources
- **SHALL** include the versionId of the current version of each `Appointment` resource returned
- **SHALL** return all appointments for the patient within the requested period signified by the `start` search parameter(s) - all appointments including cancelled appointments should be returned as part of the response, no additional filtering should be applied

- **SHALL** populate `Appointment.start`, `Appointment.end`, `Appointment.created` elements in (UK) local time in the format `yyyy-mm-ddThh:mm:ss+hh:mm`, with the timezone offset `+00:00` for UTC and `+01:00` for BST

- **SHALL** populate `Appointment.minutesDuration`

- **SHALL** populate `Appointment.serviceType.text` with the practice-defined slot type description, and where available `Appointment.serviceCategory.text` with a practice-defined schedule type description (may be called session name or rota type)

- **SHALL** meet {{pagelink:Home/Build/FHIR-Resource-Guidance.page.md}} populating all fields where data is available, excluding those listed below

- **SHALL NOT** populate the following fields:
  - `specialty`
  - `reason`

### Error handling ###

Provider systems:

- **SHALL** return a {{pagelink:Home/FHIR-Assets/All-Assets/Profiles/Profile--GPConnect-OperationOutcome-1}} resource that provides additional detail when one or more request fields are corrupt or a specific business rule/constraint is breached - refer to {{pagelink:Home/Build/Error-Handling.page.md}} for details of error codes
- **SHALL** return an error if any part of the consumer supplied date range is in the past - the OperationOutcome returned **SHALL** include a meaningful error message to indicate that the search parameters can not request appointments in the past
- where the use of the `start` search parameter does not define a valid date range, `HTTP Status code 422` with error code `INVALID_PARAMETER` will be returned - additional details **SHALL** be returned in the diagnostics element

## Examples ##

### Retrieve a patient's appointments ###

#### Request ####

Retrieve all appointments for patient with logical id 1001 which start between 2017-07-11 and 2017-09-14 inclusive:

```http

GET /Patient/1001/Appointment?start=ge2017-07-11&start=le2017-09-14

```

#### Response when the patient has appointments in the date range provided ####

The response example includes two appointments for the patient, with the organisations that made the original bookings populated as included resources.

```json
{
  "resourceType": "Bundle",
  "type": "searchset",
  "entry": [
    {
      "resource": {
        "resourceType": "Appointment",
        "id": "149",
        "meta": {
          "versionId": "1503310820000",
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
                "value": "A00123"
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
                  "code": "R0600",
                  "display": "Specialist Nurse Practitioner"
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
          "text": "Nurse Appointments"
        },
        "serviceType": [
          {
            "text": "Nurse Appointment"
          }
        ],
        "description": "GP Connect Appointment description 148",
        "start": "2017-08-21T10:30:00+01:00",
        "end": "2017-08-21T10:50:00+01:00",
        "minutesDuration": 20,
        "slot": [
          {
            "reference": "Slot/544"
          },
          {
            "reference": "Slot/545"
          }
        ],
        "created": "2017-07-09T13:48:41+01:00",
        "comment": "Test Appointment Comment 148",
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
          },
          {
            "actor": {
              "reference": "Practitioner/2"
            },
            "status": "accepted"
          }
        ]
      }
    },
    {
      "resource": {
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
        "reason": [
          {
            "text": "tennis elbow"
          }
        ],
        "description": "GP Connect Appointment description 148",
        "start": "2017-08-17T11:20:00+01:00",
        "end": "2017-08-17T11:30:00+01:00",
        "minutesDuration": 10,
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
    }
  ]
}
```

#### Response when the patient has no appointments in the date range provided ####

```json

{
  "resourceType": "Bundle",
  "type": "searchset",
  "entry": []
}
```
---