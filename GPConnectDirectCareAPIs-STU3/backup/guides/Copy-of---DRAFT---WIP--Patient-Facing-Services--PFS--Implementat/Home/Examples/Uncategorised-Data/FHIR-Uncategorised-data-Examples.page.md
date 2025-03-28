## {{page-title}}

### Access Record Structured FHIR examples for Uncategorised Data.

### Request
Example of a call to return the following items from a patient's structured record:

* Uncategorised data

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
      "name": "includeUncategorisedData",
      "part": [
        {
          "name": "uncategorisedDataSearchPeriod",
          "valuePeriod": {
            "start": "2019-01-25",
            "end": "2019-06-25"
          }
        }
      ]
    }
  ]
}
```

#### Response payload
```json
{
  "resourceType": "Bundle",
  "meta": {
    "profile": [
      "https://fhir.nhs.uk/STU3/StructureDefinition/GPConnect-StructuredRecord-Bundle-1"
    ]
  },
  "type": "collection",
  "entry": [
    {
      "resource": {
        "resourceType": "Patient",
        "id": "04603d77-1a4e-4d63-b246-d7504f8bd833",
        "meta": {
          "versionId": "1469448000000",
          "profile": [
            "https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Patient-1"
          ]
        },
        "extension": [
          {
            "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-CareConnect-GPC-RegistrationDetails-1",
            "extension": [
              {
                "url": "registrationPeriod",
                "valuePeriod": {
                  "start": "1962-07-13T00:00:00+00:00"
                }
              }
            ]
          }
        ],
        "identifier": [
          {
            "extension": [
              {
                "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-CareConnect-GPC-NHSNumberVerificationStatus-1",
                "valueCodeableConcept": {
                  "coding": [
                    {
                      "system": "https://fhir.nhs.uk/CareConnect-NHSNumberVerificationStatus-1",
                      "code": "01",
                      "display": "Number present and verified"
                    }
                  ]
                }
              }
            ],
            "system": "https://fhir.nhs.uk/Id/nhs-number",
            "value": "9999999999"
          }
        ],
        "active": true,
        "name": [
          {
            "use": "official",
            "text": "JACKSON Jane (Miss)",
            "family": "Jackson",
            "given": [
              "Jane"
            ],
            "prefix": [
              "Miss"
            ]
          }
        ],
        "telecom": [
          {
            "system": "phone",
            "value": "01454587554",
            "use": "home"
          }
        ],
        "gender": "female",
        "birthDate": "1952-05-31",
        "address": [
          {
            "use": "home",
            "type": "physical",
            "line": [
              "Cable Place",
              "Roundhay"
            ],
            "city": "Leeds",
            "district": "West Yorkshire",
            "postalCode": "LS1 5HT"
          }
        ],
        "generalPractitioner": {
          "reference": "Practitioner/6c41ebfd-57c3-4162-9d7b-208c171a2fd7"
        },
        "managingOrganization": {
          "reference": "Organization/db67f447-b30d-442a-8e31-6918d1367eeb"
        }
      }
    },
    {
      "resource": {
        "resourceType": "Organization",
        "id": "db67f447-b30d-442a-8e31-6918d1367eeb",
        "meta": {
          "versionId": "636064088098730113",
          "profile": [
            "https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Organization-1"
          ]
        },
        "identifier": [
          {
            "system": "https://fhir.nhs.uk/Id/ods-organization-code",
            "value": "O001"
          }
        ],
        "name": "The Trevelyan Practice",
        "address": [
          {
            "line": [
              "Trevelyan Square",
              "Boar Ln"
            ],
            "city": "Leeds",
            "district": "West Yorkshire",
            "postalCode": "LS1 6AE"
          }
        ],
        "telecom": [
          {
            "system": "phone",
            "value": "03003035678",
            "use": "work"
          }
        ]
      }
    },
    {
      "resource": {
        "resourceType": "Practitioner",
        "id": "6c41ebfd-57c3-4162-9d7b-208c171a2fd7",
        "meta": {
          "versionId": "1469448000000",
          "lastUpdated": "2016-07-25T12:00:00.000+00:00",
          "profile": [
            "https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Practitioner-1"
          ]
        },
        "identifier": [
          {
            "system": "https://fhir.nhs.uk/Id/sds-user-id",
            "value": "G13579135"
          }
        ],
        "name": [
          {
            "use": "usual",
            "family": "Gilbert",
            "given": [
              "Nichole"
            ],
            "prefix": [
              "Miss"
            ]
          }
        ],
        "gender": "female"
      }
    },
    {
      "resource": {
        "meta": {
          "profile": [
            "https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-PractitionerRole-1"
          ]
        },
        "resourceType": "PractitionerRole",
        "id": "e0244de8-07ef-4274-9f7a-d7067bcc8d21",
        "practitioner": {
          "reference": "Practitioner/6c41ebfd-57c3-4162-9d7b-208c171a2fd7"
        },
        "organization": {
          "reference": "Organization/db67f447-b30d-442a-8e31-6918d1367eeb"
        },
        "code": [
          {
            "coding": [
              {
                "system": "https://fhir.hl7.org.uk/STU3/CodeSystem/CareConnect-SDSJobRoleName-1",
                "code": "R0260",
                "display": "General Medical Practitioner"
              }
            ]
          }
        ]
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
        "mode": "snapshot",
        "title": "Miscellaneous record",
        "code": {
          "coding": [
            {
              "code": "826501000000100",
              "display": "Miscellaneous record",
              "system": "http://snomed.info/sct"
            }
          ]
        },
        "subject": {
          "reference": "Patient/04603d77-1a4e-4d63-b246-d7504f8bd833"
        },
        "date": "2019-03-01T10:57:34+00:00",
        "orderedBy": {
          "coding": [
            {
              "code": "event-date",
              "system": "http://hl7.org/fhir/list-order"
            }
          ]
        },
        "entry": [
          {
            "item": {
              "reference": "Observation/Consultation1-topic2-category-Examination-Observation-1"
            }
          },
          {
            "item":{
              "reference": "Observation/Consultation1-topic2-category-Examination-Observation-2"
            }
          },
          {
            "item": {
              "reference": "Observation/Consultation1-topic2-category-Examination-Observation-3"
            }
          }
        ]
      }
    },
    {
      "resource": {
        "resourceType": "Observation",
        "id": "Consultation1-topic2-category-Examination-Observation-1",
        "meta": {
          "profile": [
            "https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Observation-1"
          ]
        },
        "identifier": [
          {
            "system": "https://provider.nhs.uk/data-identifier",
            "value": "7846547856"
          }
        ],
        "status": "final",
        "code": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "code": "703421000",
              "display": "Temperature",
              "extension": {
                "url": "http://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
                "extension": [
                  {
                    "url": "DescriptionID",
                    "valueId": "3008650016"
                  },
                  {
                    "url": "descriptionDisplay",
                    "valueString": "Temperature"
                  }
                ]
              }
            }
          ]
        },
      "valueQuantity": {
        "value": 36.7,
        "unit": "C",
        "system": "http://unitsofmeasure.org",
        "code": "Cel"
      },

      "subject": {
        "reference": "Patient/04603d77-1a4e-4d63-b246-d7504f8bd833"
      },
      "issued": "2019-03-28T10:30:00+00:00",
      "performer":
  			{
            "reference": "Practitioner/6c41ebfd-57c3-4162-9d7b-208c171a2fd7"
  			},

      "effectiveDateTime": "2019-03-28T10:30:00+00:00"
    }},
    {
      "resource": {
        "resourceType": "Observation",
        "id": "Consultation1-topic2-category-Examination-Observation-2",
        "meta": {
          "profile": [
            "https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Observation-1"
          ]
        },
        "identifier": [
          {
            "system": "https://provider.nhs.uk/data-identifier",
            "value": "9834574938753498"
          }
        ],
        "status": "final",
        "code": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "code": "1097811000000106",
              "display": "Arterial oxygen saturation breathing room air at rest",
              "extension": {
                "url": "http://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
                "extension": [
                  {
                    "url": "DescriptionID",
                    "valueId": "2748921000000116"
                  },
                  {
                    "url": "descriptionDisplay",
                    "valueString": "Arterial oxygen saturation on room air at rest"
                  }
                ]
              }
            }
          ]
        },
        "valueQuantity": {
          "value": 96,
          "unit": "%",
          "system": "http://unitsofmeasure.org",
          "code": "%"
        },
        "subject": {
          "reference": "Patient/04603d77-1a4e-4d63-b246-d7504f8bd833"
        },
        "issued": "2019-03-28T10:30:00+00:00",
        "performer":
    			{
              "reference": "Practitioner/6c41ebfd-57c3-4162-9d7b-208c171a2fd7"
    			},
        "effectiveDateTime": "2019-03-28T10:30:00+00:00"
      }
    },
    {
      "resource": {
        "resourceType": "Observation",
        "id": "Consultation1-topic2-category-Examination-Observation-3",
        "meta": {
          "profile": [
            "https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Observation-1"
          ]
        },
        "identifier": [
          {
            "system": "https://provider.nhs.uk/data-identifier",
            "value": "938457984375"
          }
        ],
        "status": "final",
        "code": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "code": " 86290005",
              "display": "Respiratory rate",
              "extension": {
                "url": "http://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
                "extension": [
                  {
                    "url": "DescriptionID",
                    "valueId": "143107019"
                  },
                  {
                    "url": "descriptionDisplay",
                    "valueString": "Respiratory rate"
                  }
                ]
              }
            }
          ]
        },
        "valueQuantity": {
          "value": 16,
          "unit": "breaths per minute",
          "system": "http://unitsofmeasure.org",
          "code": "{resps}/min"
        },
        "subject": {
          "reference": "Patient/9340157B-6973-4209-9B57-BF6C64F29E46"
        },
        "issued": "2019-03-28T10:30:00+00:00",
        "performer":
    			{
              "reference": "Practitioner/6c41ebfd-57c3-4162-9d7b-208c171a2fd7"
    			},

        "effectiveDateTime": "2019-03-28T10:30:00+00:00"
      }
    }
  ]
}
```