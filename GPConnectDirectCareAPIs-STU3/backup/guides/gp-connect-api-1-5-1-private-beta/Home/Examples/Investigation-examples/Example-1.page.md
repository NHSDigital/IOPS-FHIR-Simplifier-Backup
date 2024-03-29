## {{page-title}}

### Request

Example of a call to return the following items from a patient's structured record:

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
            "city": "GREENTOWN",
            "postalCode": "LS9 7TF",
            "line": [
              "BECKETT STREET"
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
        "name": "GREENTOWN GENERAL HOSPITAL",
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
            "value": "G8040642",
            "system": "https://fhir.nhs.uk/Id/sds-user-id"
          }
        ],
        "id": "f25e9d63-6a4e-4de6-b9dc-c912fda62b01",
        "resourceType": "Practitioner",
        "name": [
          {
            "family": "SMITH",
            "given": [
              "John"
            ]
          }
        ],
        "meta": {
          "profile": [
            "https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Practitioner-1"
          ]
        }
      }
    },
    {
      "resource": {
        "gender": "female",
        "birthDate": "1974-12-29",
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
            "family": "REARDON",
            "use": "official",
            "given": [
              "John"
            ]
          }
        ],
        "meta": {
          "profile": [
            "https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Patient-1"
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
        "note": [
          {
            "text": "FBC"
          }
        ],
        "requester": {
          "agent": {
            "display": "SMITH",
            "reference": "Practitioner/f25e9d63-6a4e-4de6-b9dc-c912fda62b01"
          }
        },
        "resourceType": "ProcedureRequest",
        "performer": {
          "display": "GREENTOWN GENERAL HOSPITAL",
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
              "display": "FBC - Full blood count",
              "code": "26604007"
            }
          ]
        },
        "subject": {
          "display": "REARDON, John",
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
        "issued": "2019-04-03T12:00:00+00:00",
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
              "display": "GREENTOWN GENERAL HOSPITAL",
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
        "identifier": [
          {
            "value": "1b663fc5-9dec-49c0-90ed-18a7cfa5a6b2",
            "system": "https://tools.ietf.org/html/rfc4122"
          }
        ],
        "subject": {
          "display": "REARDON, John",
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
        "receivedTime": "2017-11-01T15:00:00+00:00",
        "resourceType": "Specimen",
        "collection": {
          "collectedDateTime": "2019-04-01T11:00:00+00:00"
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
              "display": "Venous blood specimen",
              "code": "122555007"
            }
          ]
        },
        "subject": {
          "display": "REARDON, John",
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
        "resourceType": "Observation",
        "related": [
          {
            "type": "has-member",
            "target": {
              "reference": "Observation/dacb177a-9501-4dcc-8b22-b941791ae067"
            }
          },
          {
            "type": "has-member",
            "target": {
              "reference": "Observation/32685afe-1d46-4d98-8279-39b9e96ee914"
            }
          },
          {
            "type": "has-member",
            "target": {
              "reference": "Observation/770b982d-be09-4744-a5d7-54e757947ffe"
            }
          },
          {
            "type": "has-member",
            "target": {
              "reference": "Observation/0a8aba3d-6b29-4dba-9c64-3a47516cc5eb"
            }
          },
          {
            "type": "has-member",
            "target": {
              "reference": "Observation/ddc43c3a-2863-4d6f-a926-162f5a4174b1"
            }
          },
          {
            "type": "has-member",
            "target": {
              "reference": "Observation/9825b7cf-de29-4c07-9b84-4af04dbf8233"
            }
          },
          {
            "type": "has-member",
            "target": {
              "reference": "Observation/e732e681-3a89-4433-a37b-3767dd19d809"
            }
          },
          {
            "type": "has-member",
            "target": {
              "reference": "Observation/2a604bea-1ef4-4cb1-97a0-f2a160f12679"
            }
          },
          {
            "type": "has-member",
            "target": {
              "reference": "Observation/704b6bb2-a1c0-429b-b901-c641e70345ec"
            }
          },
          {
            "type": "has-member",
            "target": {
              "reference": "Observation/53f4132c-0168-4327-8d69-560b13f5bb4e"
            }
          },
          {
            "type": "has-member",
            "target": {
              "reference": "Observation/c9e03e92-78b8-4e8e-9785-cbd9424e9380"
            }
          },
          {
            "type": "has-member",
            "target": {
              "reference": "Observation/9c61ad77-8c17-41aa-b795-f0fcb9f983d5"
            }
          },
          {
            "type": "has-member",
            "target": {
              "reference": "Observation/f67cb109-0890-4e47-9126-86da677c7008"
            }
          },
          {
            "type": "has-member",
            "target": {
              "reference": "Observation/1f2e71db-b9aa-4e4f-9a78-87f99fefc8bf"
            }
          },
          {
            "type": "has-member",
            "target": {
              "reference": "Observation/a23b563d-765a-4032-8dd3-c03178224f35"
            }
          },
          {
            "type": "has-member",
            "target": {
              "reference": "Observation/fedb7c2d-337c-435c-9169-612349783b5a"
            }
          },
          {
            "type": "has-member",
            "target": {
              "reference": "Observation/f9070943-7460-413a-a608-e15334b6e1d9"
            }
          },
          {
            "type": "has-member",
            "target": {
              "reference": "Observation/66acb40a-e241-474a-92b5-c74f9aa6a854"
            }
          }
        ],
        "status": "final",
        "performer": [
          {
            "display": "GREENTOWN GENERAL HOSPITAL",
            "reference": "Organization/d6407de7-0e86-45eb-93cb-035094aaa49e"
          }
        ],
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
              "display": "FBC - Full blood count",
              "code": "26604007"
            }
          ]
        },
        "subject": {
          "display": "REARDON, John",
          "reference": "Patient/8d6c2cd5-0eec-496a-88d0-3785a135df09"
        },
        "meta": {
          "profile": [
            "https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Observation-1"
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
                "code": "394595002"
              }
            ]
          }
        ],
        "resourceType": "Observation",
        "referenceRange": [
          {
            "high": {
              "value": 11
            },
            "low": {
              "value": 3.5
            }
          }
        ],
        "related": [
          {
            "type": "derived-from",
            "target": {
              "reference": "Observation/dacb177a-9501-4dcc-8b22-b941791ae0db"
            }
          }
        ],
        "performer": [
          {
            "display": "GREENTOWN GENERAL HOSPITAL",
            "reference": "Organization/d6407de7-0e86-45eb-93cb-035094aaa49e"
          }
        ],
        "valueQuantity": {
          "value": 5.70,
          "unit": "10*9/L"
        },
        "specimen": {
          "reference": "Specimen/756a8361-79ce-4561-afcb-a91fe19df123"
        },
        "identifier": [
          {
            "value": "2af46949-4938-4c57-bad4-c4363e1965d5",
            "system": "https://tools.ietf.org/html/rfc4122"
          }
        ],
        "id": "dacb177a-9501-4dcc-8b22-b941791ae067",
        "code": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "display": "Total white cell count",
              "code": "1022541000000102"
            }
          ]
        },
        "subject": {
          "display": "REARDON, John",
          "reference": "Patient/8d6c2cd5-0eec-496a-88d0-3785a135df09"
        },
        "status": "final",
        "meta": {
          "profile": [
            "https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Observation-1"
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
                "code": "394595002"
              }
            ]
          }
        ],
        "resourceType": "Observation",
        "referenceRange": [
                      {
            "text": "less than 3.8 to 5"
          }
        ],
        "related": [
          {
            "type": "derived-from",
            "target": {
              "reference": "Observation/dacb177a-9501-4dcc-8b22-b941791ae0db"
            }
          }
        ],
        "performer": [
          {
            "display": "GREENTOWN GENERAL HOSPITAL",
            "reference": "Organization/d6407de7-0e86-45eb-93cb-035094aaa49e"
          }
        ],
        "valueQuantity": {
          "value": 4.57,
          "unit": "10*12/L"
        },
        "specimen": {
          "reference": "Specimen/756a8361-79ce-4561-afcb-a91fe19df123"
        },
        "identifier": [
          {
            "value": "2af46949-4938-4c57-bad4-c4363e1965d5",
            "system": "https://tools.ietf.org/html/rfc4122"
          }
        ],
        "id": "32685afe-1d46-4d98-8279-39b9e96ee914",
        "code": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "display": "Red blood cell count",
              "code": "1022451000000103"
            }
          ]
        },
        "subject": {
          "display": "REARDON, John",
          "reference": "Patient/8d6c2cd5-0eec-496a-88d0-3785a135df09"
        },
        "status": "final",
        "meta": {
          "profile": [
            "https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Observation-1"
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
                "code": "394595002"
              }
            ]
          }
        ],
        "resourceType": "Observation",
        "referenceRange": [
          {
            "high": {
              "value": 150
            },
            "low": {
              "value": 115
            }
          }
        ],
        "related": [
          {
            "type": "derived-from",
            "target": {
              "reference": "Observation/dacb177a-9501-4dcc-8b22-b941791ae0db"
            }
          }
        ],
        "performer": [
          {
            "display": "GREENTOWN GENERAL HOSPITAL",
            "reference": "Organization/d6407de7-0e86-45eb-93cb-035094aaa49e"
          }
        ],
        "valueQuantity": {
          "value": 142,
          "unit": "g/dL"
        },
        "specimen": {
          "reference": "Specimen/756a8361-79ce-4561-afcb-a91fe19df123"
        },
        "identifier": [
          {
            "value": "2af46949-4938-4c57-bad4-c4363e1965d5",
            "system": "https://tools.ietf.org/html/rfc4122"
          }
        ],
        "id": "770b982d-be09-4744-a5d7-54e757947ffe",
        "code": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "display": "Haemoglobin estimation",
              "code": "1022431000000105"
            }
          ]
        },
        "subject": {
          "display": "REARDON, John",
          "reference": "Patient/8d6c2cd5-0eec-496a-88d0-3785a135df09"
        },
        "status": "final",
        "meta": {
          "profile": [
            "https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Observation-1"
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
                "code": "394595002"
              }
            ]
          }
        ],
        "resourceType": "Observation",
        "referenceRange": [
          {
            "text": "greater than 0.36 and less than 0.46"
          }
        ],
        "related": [
          {
            "type": "derived-from",
            "target": {
              "reference": "Observation/dacb177a-9501-4dcc-8b22-b941791ae0db"
            }
          }
        ],
        "performer": [
          {
            "display": "GREENTOWN GENERAL HOSPITAL",
            "reference": "Organization/d6407de7-0e86-45eb-93cb-035094aaa49e"
          }
        ],
        "valueQuantity": {
          "value": 0.42,
          "unit": "%"
        },
        "specimen": {
          "reference": "Specimen/756a8361-79ce-4561-afcb-a91fe19df123"
        },
        "identifier": [
          {
            "value": "2af46949-4938-4c57-bad4-c4363e1965d5",
            "system": "https://tools.ietf.org/html/rfc4122"
          }
        ],
        "id": "0a8aba3d-6b29-4dba-9c64-3a47516cc5eb",
        "code": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "display": "Haematocrit",
              "code": "1022291000000105"
            }
          ]
        },
        "subject": {
          "display": "REARDON, John",
          "reference": "Patient/8d6c2cd5-0eec-496a-88d0-3785a135df09"
        },
        "status": "final",
        "meta": {
          "profile": [
            "https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Observation-1"
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
                "code": "394595002"
              }
            ]
          }
        ],
        "resourceType": "Observation",
        "referenceRange": [
          {
            "high": {
              "value": 99
            },
            "low": {
              "value": 80
            }
          }
        ],
        "related": [
          {
            "type": "derived-from",
            "target": {
              "reference": "Observation/dacb177a-9501-4dcc-8b22-b941791ae0db"
            }
          }
        ],
        "performer": [
          {
            "display": "GREENTOWN GENERAL HOSPITAL",
            "reference": "Organization/d6407de7-0e86-45eb-93cb-035094aaa49e"
          }
        ],
        "valueQuantity": {
          "value": 93.40,
          "unit": "fL"
        },
        "specimen": {
          "reference": "Specimen/756a8361-79ce-4561-afcb-a91fe19df123"
        },
        "identifier": [
          {
            "value": "2af46949-4938-4c57-bad4-c4363e1965d5",
            "system": "https://tools.ietf.org/html/rfc4122"
          }
        ],
        "id": "ddc43c3a-2863-4d6f-a926-162f5a4174b1",
        "code": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "display": "Mean corpuscular volume",
              "code": "1022491000000106"
            }
          ]
        },
        "subject": {
          "display": "REARDON, John",
          "reference": "Patient/8d6c2cd5-0eec-496a-88d0-3785a135df09"
        },
        "status": "final",
        "meta": {
          "profile": [
            "https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Observation-1"
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
                "code": "394595002"
              }
            ]
          }
        ],
        "resourceType": "Observation",
        "referenceRange": [
          {
            "high": {
              "value": 32.5
            },
            "low": {
              "value": 27.5
            }
          }
        ],
        "related": [
          {
            "type": "derived-from",
            "target": {
              "reference": "Observation/dacb177a-9501-4dcc-8b22-b941791ae0db"
            }
          }
        ],
        "performer": [
          {
            "display": "GREENTOWN GENERAL HOSPITAL",
            "reference": "Organization/d6407de7-0e86-45eb-93cb-035094aaa49e"
          }
        ],
        "valueQuantity": {
          "value": 31.11,
          "unit": "pg"
        },
        "specimen": {
          "reference": "Specimen/756a8361-79ce-4561-afcb-a91fe19df123"
        },
        "identifier": [
          {
            "value": "2af46949-4938-4c57-bad4-c4363e1965d5",
            "system": "https://tools.ietf.org/html/rfc4122"
          }
        ],
        "id": "9825b7cf-de29-4c07-9b84-4af04dbf8233",
        "code": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "display": "Mean corpuscular haemoglobin",
              "code": "1022471000000107"
            }
          ]
        },
        "subject": {
          "display": "REARDON, John",
          "reference": "Patient/8d6c2cd5-0eec-496a-88d0-3785a135df09"
        },
        "status": "final",
        "meta": {
          "profile": [
            "https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Observation-1"
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
                "code": "394595002"
              }
            ]
          }
        ],
        "resourceType": "Observation",
        "referenceRange": [
          {
            "high": {
              "value": 350
            },
            "low": {
              "value": 310
            }
          }
        ],
        "related": [
          {
            "type": "derived-from",
            "target": {
              "reference": "Observation/dacb177a-9501-4dcc-8b22-b941791ae0db"
            }
          }
        ],
        "performer": [
          {
            "display": "GREENTOWN GENERAL HOSPITAL",
            "reference": "Organization/d6407de7-0e86-45eb-93cb-035094aaa49e"
          }
        ],
        "valueQuantity": {
          "value": 333,
          "unit": "g/dL"
        },
        "specimen": {
          "reference": "Specimen/756a8361-79ce-4561-afcb-a91fe19df123"
        },
        "identifier": [
          {
            "value": "2af46949-4938-4c57-bad4-c4363e1965d5",
            "system": "https://tools.ietf.org/html/rfc4122"
          }
        ],
        "id": "e732e681-3a89-4433-a37b-3767dd19d809",
        "code": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "display": "Mean corpuscular haemoglobin concentration",
              "code": "1022481000000109"
            }
          ]
        },
        "subject": {
          "display": "REARDON, John",
          "reference": "Patient/8d6c2cd5-0eec-496a-88d0-3785a135df09"
        },
        "status": "final",
        "meta": {
          "profile": [
            "https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Observation-1"
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
                "code": "394595002"
              }
            ]
          }
        ],
        "resourceType": "Observation",
        "referenceRange": [
          {
            "high": {
              "value": 400
            },
            "low": {
              "value": 140
            }
          }
        ],
        "related": [
          {
            "type": "derived-from",
            "target": {
              "reference": "Observation/dacb177a-9501-4dcc-8b22-b941791ae0db"
            }
          }
        ],
        "performer": [
          {
            "display": "GREENTOWN GENERAL HOSPITAL",
            "reference": "Organization/d6407de7-0e86-45eb-93cb-035094aaa49e"
          }
        ],
        "valueQuantity": {
          "value": 206,
          "unit": "10*9/L"
        },
        "specimen": {
          "reference": "Specimen/756a8361-79ce-4561-afcb-a91fe19df123"
        },
        "identifier": [
          {
            "value": "2af46949-4938-4c57-bad4-c4363e1965d5",
            "system": "https://tools.ietf.org/html/rfc4122"
          }
        ],
        "id": "2a604bea-1ef4-4cb1-97a0-f2a160f12679",
        "code": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "display": "Platelet count",
              "code": "1022651000000100"
            }
          ]
        },
        "subject": {
          "display": "REARDON, John",
          "reference": "Patient/8d6c2cd5-0eec-496a-88d0-3785a135df09"
        },
        "status": "final",
        "meta": {
          "profile": [
            "https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Observation-1"
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
                "code": "394595002"
              }
            ]
          }
        ],
        "resourceType": "Observation",
        "referenceRange": [
          {
            "high": {
              "value": 8
            },
            "low": {
              "value": 1.7
            }
          }
        ],
        "related": [
          {
            "type": "derived-from",
            "target": {
              "reference": "Observation/dacb177a-9501-4dcc-8b22-b941791ae0db"
            }
          }
        ],
        "performer": [
          {
            "display": "GREENTOWN GENERAL HOSPITAL",
            "reference": "Organization/d6407de7-0e86-45eb-93cb-035094aaa49e"
          }
        ],
        "valueQuantity": {
          "value": 2.75,
          "unit": "10*9/L"
        },
        "specimen": {
          "reference": "Specimen/756a8361-79ce-4561-afcb-a91fe19df123"
        },
        "identifier": [
          {
            "value": "2af46949-4938-4c57-bad4-c4363e1965d5",
            "system": "https://tools.ietf.org/html/rfc4122"
          }
        ],
        "id": "704b6bb2-a1c0-429b-b901-c641e70345ec",
        "code": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "display": "Neutrophil count",
              "code": "1022551000000104"
            }
          ]
        },
        "subject": {
          "display": "REARDON, John",
          "reference": "Patient/8d6c2cd5-0eec-496a-88d0-3785a135df09"
        },
        "status": "final",
        "meta": {
          "profile": [
            "https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Observation-1"
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
                "code": "394595002"
              }
            ]
          }
        ],
        "resourceType": "Observation",
        "performer": [
          {
            "display": "ST JAMES'S UNIVERSITY HOSPITAL",
            "reference": "Organization/d6407de7-0e86-45eb-93cb-035094aaa49e"
          }
        ],
        "related": [
          {
            "type": "derived-from",
            "target": {
              "reference": "Observation/dacb177a-9501-4dcc-8b22-b941791ae0db"
            }
          }
        ],
        "valueQuantity": {
          "value": 77.73,
          "unit": "%"
        },
        "specimen": {
          "reference": "Specimen/756a8361-79ce-4561-afcb-a91fe19df123"
        },
        "identifier": [
          {
            "value": "2af46949-4938-4c57-bad4-c4363e1965d5",
            "system": "https://tools.ietf.org/html/rfc4122"
          }
        ],
        "id": "53f4132c-0168-4327-8d69-560b13f5bb4e",
        "code": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "display": "Percentage neutrophils",
              "code": "1015471000000105"
            }
          ]
        },
        "subject": {
          "display": "REARDON, John",
          "reference": "Patient/8d6c2cd5-0eec-496a-88d0-3785a135df09"
        },
        "status": "final",
        "meta": {
          "profile": [
            "https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Observation-1"
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
                "code": "394595002"
              }
            ]
          }
        ],
        "resourceType": "Observation",
        "referenceRange": [
          {
            "high": {
              "value": 4
            },
            "low": {
              "value": 1
            }
          }
        ],
        "related": [
          {
            "type": "derived-from",
            "target": {
              "reference": "Observation/dacb177a-9501-4dcc-8b22-b941791ae0db"
            }
          }
        ],
        "performer": [
          {
            "display": "GREENTOWN GENERAL HOSPITAL",
            "reference": "Organization/d6407de7-0e86-45eb-93cb-035094aaa49e"
          }
        ],
        "valueQuantity": {
          "value": 2.12,
          "unit": "10*9/L"
        },
        "specimen": {
          "reference": "Specimen/756a8361-79ce-4561-afcb-a91fe19df123"
        },
        "identifier": [
          {
            "value": "2af46949-4938-4c57-bad4-c4363e1965d5",
            "system": "https://tools.ietf.org/html/rfc4122"
          }
        ],
        "id": "c9e03e92-78b8-4e8e-9785-cbd9424e9380",
        "code": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "display": "Lymphocyte count",
              "code": "1022581000000105"
            }
          ]
        },
        "subject": {
          "display": "REARDON, John",
          "reference": "Patient/8d6c2cd5-0eec-496a-88d0-3785a135df09"
        },
        "status": "final",
        "meta": {
          "profile": [
            "https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Observation-1"
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
                "code": "394595002"
              }
            ]
          }
        ],
        "resourceType": "Observation",
        "performer": [
          {
            "display": "GREENTOWN GENERAL HOSPITAL",
            "reference": "Organization/d6407de7-0e86-45eb-93cb-035094aaa49e"
          }
        ],
        "related": [
          {
            "type": "derived-from",
            "target": {
              "reference": "Observation/dacb177a-9501-4dcc-8b22-b941791ae0db"
            }
          }
        ],
        "valueQuantity": {
          "value": 14.30,
          "unit": "%"
        },
        "specimen": {
          "reference": "Specimen/756a8361-79ce-4561-afcb-a91fe19df123"
        },
        "identifier": [
          {
            "value": "2af46949-4938-4c57-bad4-c4363e1965d5",
            "system": "https://tools.ietf.org/html/rfc4122"
          }
        ],
        "id": "9c61ad77-8c17-41aa-b795-f0fcb9f983d5",
        "code": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "display": "Percentage lymphocytes",
              "code": "1015481000000107"
            }
          ]
        },
        "subject": {
          "display": "REARDON, John",
          "reference": "Patient/8d6c2cd5-0eec-496a-88d0-3785a135df09"
        },
        "status": "final",
        "meta": {
          "profile": [
            "https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Observation-1"
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
                "code": "394595002"
              }
            ]
          }
        ],
        "resourceType": "Observation",
        "referenceRange": [
          {
            "text": "greater than 0.2 to greater than 0.8"
          }
        ],
        "performer": [
          {
            "display": "GREENTOWN GENERAL HOSPITAL",
            "reference": "Organization/d6407de7-0e86-45eb-93cb-035094aaa49e"
          }
        ],
        "related": [
          {
            "type": "derived-from",
            "target": {
              "reference": "Observation/dacb177a-9501-4dcc-8b22-b941791ae0db"
            }
          }
        ],
        "valueQuantity": {
          "value": 0.47,
          "unit": "10*9/L"
        },
        "specimen": {
          "reference": "Specimen/756a8361-79ce-4561-afcb-a91fe19df123"
        },
        "identifier": [
          {
            "value": "2af46949-4938-4c57-bad4-c4363e1965d5",
            "system": "https://tools.ietf.org/html/rfc4122"
          }
        ],
        "id": "f67cb109-0890-4e47-9126-86da677c7008",
        "code": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "display": "Monocyte count",
              "code": "1022591000000107"
            }
          ]
        },
        "subject": {
          "display": "REARDON, John",
          "reference": "Patient/8d6c2cd5-0eec-496a-88d0-3785a135df09"
        },
        "status": "final",
        "meta": {
          "profile": [
            "https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Observation-1"
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
                "code": "394595002"
              }
            ]
          }
        ],
        "resourceType": "Observation",
        "performer": [
          {
            "display": "GREENTOWN GENERAL HOSPITAL",
            "reference": "Organization/d6407de7-0e86-45eb-93cb-035094aaa49e"
          }
        ],
        "related": [
          {
            "type": "derived-from",
            "target": {
              "reference": "Observation/dacb177a-9501-4dcc-8b22-b941791ae0db"
            }
          }
        ],
        "valueQuantity": {
          "value": 7.09,
          "unit": "%"
        },
        "specimen": {
          "reference": "Specimen/756a8361-79ce-4561-afcb-a91fe19df123"
        },
        "identifier": [
          {
            "value": "2af46949-4938-4c57-bad4-c4363e1965d5",
            "system": "https://tools.ietf.org/html/rfc4122"
          }
        ],
        "id": "1f2e71db-b9aa-4e4f-9a78-87f99fefc8bf",
        "code": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "display": "Percentage monocytes",
              "code": "1015491000000109"
            }
          ]
        },
        "subject": {
          "display": "REARDON, John",
          "reference": "Patient/8d6c2cd5-0eec-496a-88d0-3785a135df09"
        },
        "status": "final",
        "meta": {
          "profile": [
            "https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Observation-1"
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
                "code": "394595002"
              }
            ]
          }
        ],
        "resourceType": "Observation",
        "referenceRange": [
          {
            "text": "greater than 0.04 to greater than 0.4"
          }
        ],
        "related": [
          {
            "type": "derived-from",
            "target": {
              "reference": "Observation/dacb177a-9501-4dcc-8b22-b941791ae0db"
            }
          }
        ],
        "performer": [
          {
            "display": "GREENTOWN GENERAL HOSPITAL",
            "reference": "Organization/d6407de7-0e86-45eb-93cb-035094aaa49e"
          }
        ],
        "valueQuantity": {
          "value": 0.28,
          "unit": "10*9/L"
        },
        "specimen": {
          "reference": "Specimen/756a8361-79ce-4561-afcb-a91fe19df123"
        },
        "identifier": [
          {
            "value": "2af46949-4938-4c57-bad4-c4363e1965d5",
            "system": "https://tools.ietf.org/html/rfc4122"
          }
        ],
        "id": "a23b563d-765a-4032-8dd3-c03178224f35",
        "code": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "display": "Eosinophil count",
              "code": "1022561000000101"
            }
          ]
        },
        "subject": {
          "display": "REARDON, John",
          "reference": "Patient/8d6c2cd5-0eec-496a-88d0-3785a135df09"
        },
        "status": "final",
        "meta": {
          "profile": [
            "https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Observation-1"
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
                "code": "394595002"
              }
            ]
          }
        ],
        "resourceType": "Observation",
        "performer": [
          {
            "display": "GREENTOWN GENERAL HOSPITAL",
            "reference": "Organization/d6407de7-0e86-45eb-93cb-035094aaa49e"
          }
        ],
        "related": [
          {
            "type": "derived-from",
            "target": {
              "reference": "Observation/dacb177a-9501-4dcc-8b22-b941791ae0db"
            }
          }
        ],
        "valueQuantity": {
          "value": 0.92,
          "unit": "%"
        },
        "specimen": {
          "reference": "Specimen/756a8361-79ce-4561-afcb-a91fe19df123"
        },
        "identifier": [
          {
            "value": "2af46949-4938-4c57-bad4-c4363e1965d5",
            "system": "https://tools.ietf.org/html/rfc4122"
          }
        ],
        "id": "fedb7c2d-337c-435c-9169-612349783b5a",
        "code": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "display": "Percentage eosinophils",
              "code": "1015561000000104"
            }
          ]
        },
        "subject": {
          "display": "REARDON, John",
          "reference": "Patient/8d6c2cd5-0eec-496a-88d0-3785a135df09"
        },
        "status": "final",
        "meta": {
          "profile": [
            "https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Observation-1"
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
                "code": "394595002"
              }
            ]
          }
        ],
        "resourceType": "Observation",
        "referenceRange": [
          {
            "high": {
              "value": 0.10
            },
            "low": {
              "value": 0.02
            }
          }
        ],
        "related": [
          {
            "type": "derived-from",
            "target": {
              "reference": "Observation/dacb177a-9501-4dcc-8b22-b941791ae0db"
            }
          }
        ],
        "performer": [
          {
            "display": "GREENTOWN GENERAL HOSPITAL",
            "reference": "Organization/d6407de7-0e86-45eb-93cb-035094aaa49e"
          }
        ],
        "valueQuantity": {
          "value": 0.05,
          "unit": "10*9/L"
        },
        "specimen": {
          "reference": "Specimen/756a8361-79ce-4561-afcb-a91fe19df123"
        },
        "identifier": [
          {
            "value": "2af46949-4938-4c57-bad4-c4363e1965d5",
            "system": "https://tools.ietf.org/html/rfc4122"
          }
        ],
        "id": "f9070943-7460-413a-a608-e15334b6e1d9",
        "code": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "display": "Basophil count",
              "code": "1022571000000108"
            }
          ]
        },
        "subject": {
          "display": "REARDON, John",
          "reference": "Patient/8d6c2cd5-0eec-496a-88d0-3785a135df09"
        },
        "status": "final",
        "meta": {
          "profile": [
            "https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Observation-1"
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
                "code": "394595002"
              }
            ]
          }
        ],
        "resourceType": "Observation",
        "performer": [
          {
            "display": "GREENTOWN GENERAL HOSPITAL",
            "reference": "Organization/d6407de7-0e86-45eb-93cb-035094aaa49e"
          }
        ],
        "related": [
          {
            "type": "derived-from",
            "target": {
              "reference": "Observation/dacb177a-9501-4dcc-8b22-b941791ae0db"
            }
          }
        ],
        "valueQuantity": {
          "value": 0,
          "unit": "%"
        },
        "specimen": {
          "reference": "Specimen/756a8361-79ce-4561-afcb-a91fe19df123"
        },
        "identifier": [
          {
            "value": "2af46949-4938-4c57-bad4-c4363e1965d5",
            "system": "https://tools.ietf.org/html/rfc4122"
          }
        ],
        "id": "66acb40a-e241-474a-92b5-c74f9aa6a854",
        "code": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "display": "Percentage basophils",
              "code": "1015501000000103"
            }
          ]
        },
        "subject": {
          "display": "REARDON, John",
          "reference": "Patient/8d6c2cd5-0eec-496a-88d0-3785a135df09"
        },
        "status": "final",
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