## {{page-title}}


## FHIR relative request
```FHIR

GET /Patient/[id]/Appointment?start=ge[lower_date_range_boundary]&start=le[upper_date_range_boundary]

```

## FHIR absolute request

```FHIR
GET https://[proxy_server]/https://[provider_server]/[fhir_base]/Patient/[id]/Appointment?start=ge[lower_date_range_boundary]&start=le[upper_date_range_boundary]
```

## Example request

Retrieve all appointments for patient with logical id 1001 which start on or between 2017-07-11 and 2017-09-14:

```FHIR
GET /Patient/1001/Appointment?start=ge2017-07-11&start=le2017-09-14
```

## Example response

```json

{
  "resourceType": "Bundle",
  "type": "searchset",
  "entry": [
    {
      "resource": {
        "resourceType": "Appointment",
        "id": "148",
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
        "start": "2017-08-21T10:20:00+01:00",
        "end": "2017-08-21T10:50:00+01:00",
        "slot": [
          {
            "reference": "Slot/544"
          },
          {
            "reference": "Slot/545"
          },
          {
            "reference": "Slot/546"
          }
        ],
        "created": "2017-07-09T13:48:41+01:00",
        "comment": "Test Appointment Comment 148",
        "participant": [
          {
            "actor": {
              "reference": "Patient/2"
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
        "id": "149",
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
            "name": "Test Organization Name 2",
            "telecom": [
              {
                "system": "phone",
                "value": "0300 303 5679"
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
        "start": "2016-08-16T11:20:00+01:00",
        "end": "2016-08-16T11:30:00+01:00",
        "slot": [
          {
            "reference": "Slot/303"
          }
        ],
        "created": "2016-08-14T13:48:41+01:00",
        "participant": [
          {
            "actor": {
              "reference": "Patient/2"
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
---