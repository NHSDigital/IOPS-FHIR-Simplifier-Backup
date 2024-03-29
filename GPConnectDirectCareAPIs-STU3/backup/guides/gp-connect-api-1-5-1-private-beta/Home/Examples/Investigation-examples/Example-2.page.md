## {{page-title}}

### Request

Example of a call to return the following items from a patient’s structured record:

- Investigations

#### Request payload

```json
{
  "meta": {
    "profile": [
      "https://fhir.nhs.uk/STU3/OperationDefinition/GPConnect-GetStructuredRecord-Operation-1"
    ]
  },
  "resourceType": "Parameters",
  "parameter": [
    {
      "name": "patientNHSNumber",
      "valueIdentifier": {
        "system": "https://fhir.nhs.uk/Id/nhs-number",
        "value": "9432003812"
      }
    },
    {
      "name": "includeInvestigations",
      "part": [
        {
          "name": "investigationSearchPeriod",
          "valuePeriod": {
            "start": "2017-01-02",
            "end": "2017-07-02"
          }
        }
      ]
    }
  ]
}
```

### Response

#### Response payload

```json
{
  "resourceType": "Bundle",
  "type": "collection",
  "meta": {
    "profile": [
      "https://fhir.nhs.uk/STU3/StructureDefinition/GPConnect-StructuredRecord-Bundle-1"
    ]
  },
  "entry": [
    {
      "resource": {
        "address": [
          {
            "district": "WEST YORKSHIRE",
            "city": "BRADFORD",
            "postalCode": "BD9 6DP",
            "line": [
              "HEIGHTS LANE"
            ]
          }
        ],
        "identifier": [
          {
            "value": "RGD12",
            "system": "https://fhir.nhs.uk/Id/ods-organization-code"
          }
        ],
        "id": "d6407de7-0e86-45eb-93cb-035094aaa49e",
        "resourceType": "Organization",
        "name": "LINGFIELD ROYAL INFIRMARY",
        "meta": {
          "profile": [
            "https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Organization-1"
          ]
        }
      }
    },
    {
      "resource": {
        "identifier": [
          {
            "value": "C8040642",
            "system": "https://fhir.nhs.uk/Id/sds-user-id"
          }
        ],
        "id": "f25e9d63-6a4e-4de6-b9dc-c912fda62b01",
        "resourceType": "Practitioner",
        "name": [
          {
            "family": "kahn",
            "given": [
              "Ibrahim"
            ]
          }
        ],
        "meta": {
          "profile": [
            "https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-Practitioner-1"
          ]
        }
      }
    },
    {
      "resource": {
        "gender": "female",
        "birthDate": "1961-01-03",
        "identifier": [
          {
            "value": "9432003812",
            "system": "https://fhir.nhs.uk/Id/nhs-number",
            "extension": [
              {
                "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-NHSNumberVerificationStatus-1",
                "valueCodeableConcept": {
                  "coding": [
                    {
                      "system": "https://fhir.hl7.org.uk/STU3/CodeSystem/CareConnect-NHSNumberVerificationStatus-1",
                      "display": "Number present and verified",
                      "code": "01"
                    }
                  ]
                }
              }
            ]
          }
        ],
        "id": "8d6c2cd5-0eec-496a-88d0-3785a135df09",
        "resourceType": "Patient",
        "name": [
          {
            "family": "KAY",
            "use": "official",
            "given": [
              "Michael"
            ]
          }
        ],
        "meta": {
          "profile": [
            "https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-Patient-1"
          ]
        }
      }
    },
    {
      "resource": {
        "note": [
          {
            "text": "High Blood Sugar"
          }
        ],
        "requester": {
          "agent": {
            "display": "SCOTT",
            "reference": "Practitioner/f25e9d63-6a4e-4de6-b9dc-c912fda62b01"
          }
        },
        "resourceType": "ProcedureRequest",
        "performer": {
          "display": "ST JAMES'S UNIVERSITY HOSPITAL",
          "reference": "Organization/d6407de7-0e86-45eb-93cb-035094aaa49e"
        },
        "intent": "order",
        "status": "active",
        "identifier": [
          {
            "value": "7e9bbd01-4e52-420d-b05b-48bc671d6708",
            "system": "https://tools.ietf.org/html/rfc4122"
          }
        ],
        "id": "d9df1431-22ac-462a-946a-f195f6c639af",
        "code": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "display": "Prostate specific antigen measurement",
              "code": "63476009"
            }
          ]
        },
        "subject": {
          "display": "KAY, Michael",
          "reference": "Patient/8d6c2cd5-0eec-496a-88d0-3785a135df09"
        },
        "meta": {
          "profile": [
            "https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-ProcedureRequest-1"
          ]
        }
      }
    },
    {
      "resource": {
        "resourceType": "List",
        "meta": {
          "profile": [
            "https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"
          ]
        },
        "status": "current",
        "title": "Investigations and Results",
        "code": {
          "coding": [
            {
              "display": "Investigations and Results",
              "system": "http://snomed.info/sct",
              "code": "887191000000108"
            }
          ]
        },
        "entry": [
          {
            "item": {
              "reference": "DiagnosticReport/efae5859-28df-4e7d-be91-6df56d8215e4"
            }
          }
        ],
        "date": "2018-03-01T10:57:34+00:00",
        "mode": "snapshot",
        "orderedBy": {
          "coding": [
            {
              "system": "http://hl7.org/fhir/list-order",
              "code": "event-date"
            }
          ]
        },
        "subject": {
          "reference": "Patient/8d6c2cd5-0eec-496a-88d0-3785a135df09"
        }
      }
    },
    {
      "resource": {
        "issued": "2019-03-03T12:00:00+00:00",
        "result": [
          {
            "reference": "Observation/dacb177a-9501-4dcc-8b22-b941791ae0db"
          }
        ],
        "basedOn": [
          {
            "reference": "ProcedureRequest/d9df1431-22ac-462a-946a-f195f6c639af"
          }
        ],
        "status": "final",
        "performer": [
          {
            "actor": {
              "display": "ST JAMES'S UNIVERSITY HOSPITAL",
              "reference": "Organization/d6407de7-0e86-45eb-93cb-035094aaa49e"
            }
          }
        ],
        "specimen": [
          {
            "reference": "Specimen/756a8361-79ce-4561-afcb-a91fe19df123"
          }
        ],
        "resourceType": "DiagnosticReport",
        "id": "efae5859-28df-4e7d-be91-6df56d8215e4",
        "code": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "display": "Diagnostic studies report",
              "code": "721981007"
            }
          ]
        },
        "subject": {
          "display": "KAY, Michael",
          "reference": "Patient/8d6c2cd5-0eec-496a-88d0-3785a135df09"
        },
        "meta": {
          "profile": [
            "https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-DiagnosticReport-1"
          ]
        }
      }
    },
    {
      "resource": {
        "receivedTime": "2019-01-29T15:00:00+00:00",
        "resourceType": "Specimen",
        "collection": {
          "collectedDateTime": "2017-11-01T11:00:00+00:00",
          "quantity": {
            "value": 11,
            "unit": "ng/mL"
          }
        },
        "status": "available",
        "identifier": [
          {
            "value": "1b663fc5-9dec-49c0-9eed-18a7cfa5a6b2",
            "system": "https://tools.ietf.org/html/rfc4122"
          }
        ],
        "id": "756a8361-79ce-4561-afcb-a91fe19df123",
        "type": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "display": "Venous blood (substance)",
              "code": "53130003"
            }
          ]
        },
        "subject": {
          "display": "KAY, Michael",
          "reference": "Patient/8d6c2cd5-0eec-496a-88d0-3785a135df09"
        },
        "meta": {
          "profile": [
            "https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Specimen-1"
          ]
        }
      }
    },
    {
      "resource": {
        "category": [
          {
            "coding": [
              {
                "system": "http://snomed.info/sct",
                "display": "Pathology",
                "code": "394595002 "
              }
            ]
          }
        ],
        "referenceRange": [
          {
            "high": {
              "value": 4
            },
            "low": {
              "value": 0
            }
          }
        ],
        "resourceType": "Observation",
        "status": "final",
        "valueQuantity": {
          "value": 5.90,
          "unit": "ug/L"
        },
        "performer": [
          {
            "display": "ST JAMES'S UNIVERSITY HOSPITAL",
            "reference": "Organization/d6407de7-0e86-45eb-93cb-035094aaa49e"
          }
        ],
        "effectiveDateTime": "2017-11-01T15:00:00+00:00",
        "specimen": {
          "reference": "Specimen/756a8361-79ce-4561-afcb-a91fe19df123"
        },
        "identifier": [
          {
            "value": "2af46949-4938-4c57-bad4-c4363e1965d5",
            "system": "https://tools.ietf.org/html/rfc4122"
          }
        ],
        "id": "dacb177a-9501-4dcc-8b22-b941791ae0db",
        "code": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "display": "Prostate specific antigen level",
              "code": "1030791000000100"
            }
          ]
        },
        "subject": {
          "display": "KAY, Michael",
          "reference": "Patient/8d6c2cd5-0eec-496a-88d0-3785a135df09"
        },
        "meta": {
          "profile": [
            "https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Observation-1"
          ]
        }
      }
    }
  ]
}
```