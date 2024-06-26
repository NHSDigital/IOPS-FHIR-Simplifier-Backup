## {{page-title}}

### Request

Example of a call to return the following items from a patient's structured record:

- Allergies
- Resolved allergies

#### Request payload

```json
{
  "resourceType": "Parameters",
  "parameter": [
    {
      "name": "patientNHSNumber",
      "valueIdentifier": {
        "system": "https://fhir.nhs.uk/Id/nhs-number",
        "value": "9999999999"
      }
    },
    {
      "name": "includeAllergies",
      "part": [
        {
          "name": "includeResolvedAllergies",
          "valueBoolean": true
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
        "generalPractitioner": [
          {
            "reference": "Practitioner/6c41ebfd-57c3-4162-9d7b-208c171a2fd7"
          }
        ],
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
        "title": "Active Allergies",
        "code": {
          "coding": [
            {
              "display": "Allergies and adverse reaction",
              "system": "http://snomed.info/sct",
              "code": "886921000000105"
            }
          ]
        },
        "entry": [
          {
            "item": {
              "reference": "AllergyIntolerance/561850bd-360c-4d17-b3c8-a837ef0cbfba"
            }
          },
          {
            "item": {
              "reference": "AllergyIntolerance/6bff710a-0bdc-4c9b-b98b-40db0a107edc"
            }
          },
          {
            "item": {
              "reference": "AllergyIntolerance/5eb0f76a-cecb-4b83-999d-ddb76e551a9b"
            }
          },
          {
            "item": {
              "reference": "AllergyIntolerance/d92b7d42-554d-4c92-b829-e76508185702"
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
          "reference": "Patient/04603d77-1a4e-4d63-b246-d7504f8bd833"
        }
      }
    },
    {
      "resource": {
        "resourceType": "List",
        "contained": [
          {
            "resourceType": "AllergyIntolerance",
            "id": "Resolved-1",
            "identifier": [
              {
                "system": "https://provider.nhs.uk/data-identifier",
                "value": "83426283749629"
              }
            ],
            "extension": [
              {
                "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-CareConnect-GPC-AllergyIntoleranceEnd-1",
                "extension": [
                  {
                    "url": "endDate",
                    "valueDateTime": "2018-03-01"
                  },
                  {
                    "url": "reasonEnded",
                    "valueString": "Patient reports no subsequent recurrence on same medication"
                  }
                ]
              }
            ],
            "reaction": [
              {
                "manifestation": [
                  {
                    "coding": [
                      {
                        "display": "Vomiting",
                        "code": "422400008",
                        "system": "http://snomed.info/sct",
                        "extension": [
                          {
                            "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
                            "extension": [
                              {
                                "url": "DescriptionID",
                                "valueId": "2647992016"
                              },
                              {
                                "url": "DescriptionDisplay",
                                "valueString": "Emesis"
                              }
                            ]
                          }
                        ]
                      }
                    ]
                  }
                ],
                "severity": "severe"
              }
            ],
            "verificationStatus": "unconfirmed",
            "assertedDate": "2011-05-07T00:00:00+00:00",
            "type": "intolerance",
            "code": {
              "coding": [
                {
                  "display": "Aspirin 75mg dispersible tablet",
                  "code": "319773006",
                  "system": "http://snomed.info/sct",
                  "extension": [
                    {
                      "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
                      "extension": [
                        {
                          "url": "DescriptionID",
                          "valueId": "56962301000001119"
                        }
                      ]
                    }
                  ]
                }
              ]
            },
            "clinicalStatus": "resolved",
            "patient": {
              "reference": "Patient/04603d77-1a4e-4d63-b246-d7504f8bd833"
            },
            "note": [
              {
                "text": "Allergy Type: Adverse Reaction, Certainty: Absolute, Severity: Very Severe, NOTES: Some freetext notes"
              }
            ],
            "recorder": {
              "reference": "PractitionerRole/e0244de8-07ef-4274-9f7a-d7067bcc8d21"
            },
            "category": [
              "medication"
            ],
            "meta": {
              "profile": [
                "https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-AllergyIntolerance-1"
              ]
            },
            "criticality": "low"
          }
        ],
        "meta": {
          "profile": [
            "https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"
          ]
        },
        "status": "current",
        "title": "Resolved Allergies",
        "code": {
          "coding": [
            {
              "display": "Resolved Allergies",
              "system": "http://snomed.info/sct",
              "code": "TBD"
            }
          ]
        },
        "entry": [
          {
            "item": {
              "reference": "#Resolved-1"
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
          "identifier": {
            "system": "https://fhir.nhs.uk/Id/nhs-number",
            "value": "1234567890"
          }
        }
      }
    },
    {
      "resource": {
        "resourceType": "AllergyIntolerance",
        "id": "6bff710a-0bdc-4c9b-b98b-40db0a107edc",
        "identifier": [
          {
            "system": "https://provider.nhs.uk/data-identifier",
            "value": "83426283749639"
          }
        ],
        "reaction": [
          {
            "manifestation": [
              {
                "coding": [
                  {
                    "display": "O/E - itchy rash",
                    "code": "304386008",
                    "system": "http://snomed.info/sct",
                    "extension": [
                      {
                        "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
                        "extension": [
                          {
                            "url": "DescriptionID",
                            "valueId": "446685017"
                          }
                        ]
                      }
                    ]
                  }
                ]
              }
            ],
            "severity": "mild"
          }
        ],
        "verificationStatus": "unconfirmed",
        "assertedDate": "2012-05-07T00:00:00+00:00",
        "type": "allergy",
        "code": {
          "coding": [
            {
              "display": "Amoxicillin 250mg capsules",
              "code": "323509004",
              "system": "http://snomed.info/sct",
              "extension": [
                {
                  "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
                  "extension": [
                    {
                      "url": "DescriptionID",
                      "valueId": "56966201000001112"
                    }
                  ]
                }
              ]
            }
          ]
        },
        "clinicalStatus": "active",
        "patient": {
          "reference": "Patient/04603d77-1a4e-4d63-b246-d7504f8bd833"
        },
        "note": [
          {
            "text": "Certainty: Likely, Severity: Minimal, NOTES: Some freetext notes"
          }
        ],
        "recorder": {
          "reference": "PractitionerRole/e0244de8-07ef-4274-9f7a-d7067bcc8d21"
        },
        "category": [
          "medication"
        ],
        "meta": {
          "profile": [
            "https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-AllergyIntolerance-1"
          ]
        },
        "criticality": "low"
      }
    },
    {
      "resource": {
        "resourceType": "AllergyIntolerance",
        "id": "5eb0f76a-cecb-4b83-999d-ddb76e551a9b",
        "identifier": [
          {
            "system": "https://provider.nhs.uk/data-identifier",
            "value": "83426283749649"
          }
        ],
        "reaction": [
          {
            "manifestation": [
              {
                "coding": [
                  {
                    "display": "Peanut-induced anaphylaxis",
                    "code": "241933001",
                    "system": "http://snomed.info/sct",
                    "extension": [
                      {
                        "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
                        "extension": [
                          {
                            "url": "DescriptionID",
                            "valueId": "362151013"
                          }
                        ]
                      }
                    ]
                  }
                ],
                "text": "Anaphalactic shock"
              }
            ],
            "severity": "severe"
          }
        ],
        "verificationStatus": "unconfirmed",
        "assertedDate": "2016-02-08T10:57:34+00:00",
        "type": "allergy",
        "code": {
          "coding": [
            {
              "display": "Peanut - dietary",
              "code": "256349002",
              "system": "http://snomed.info/sct",
              "extension": [
                {
                  "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
                  "extension": [
                    {
                      "url": "DescriptionID",
                      "valueId": "381852012"
                    },
                    {
                      "url": "DescriptionDisplay",
                      "valueString": "Peanut"
                    }
                  ]
                }
              ]
            }
          ],
          "text": "Nut allergy"
        },
        "clinicalStatus": "active",
        "patient": {
          "reference": "Patient/04603d77-1a4e-4d63-b246-d7504f8bd833"
        },
        "note": [
          {
            "text": "Certainty: Certain, Severity: Life Threatening, NOTES: notes on the peanut allergy"
          }
        ],
        "recorder": {
          "reference": "PractitionerRole/e0244de8-07ef-4274-9f7a-d7067bcc8d21"
        },
        "category": [
          "environment"
        ],
        "meta": {
          "profile": [
            "https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-AllergyIntolerance-1"
          ]
        },
        "criticality": "high"
      }
    },
    {
      "resource": {
        "resourceType": "AllergyIntolerance",
        "id": "d92b7d42-554d-4c92-b829-e76508185702",
        "identifier": [
          {
            "system": "https://provider.nhs.uk/data-identifier",
            "value": "83426283749659"
          }
        ],
        "verificationStatus": "unconfirmed",
        "type": "allergy",
        "code": {
          "coding": [
            {
              "display": "Transfer-degraded drug allergy",
              "code": "196461000000101",
              "system": "http://snomed.info/sct",
              "extension": [
                {
                  "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
                  "extension": [
                    {
                      "url": "DescriptionID",
                      "valueId": "294801000000114"
                    }
                  ]
                }
              ]
            }
          ],
          "text": "Allergy to paracetemol"
        },
        "clinicalStatus": "active",
        "patient": {
          "reference": "Patient/04603d77-1a4e-4d63-b246-d7504f8bd833"
        },
        "note": [
          {
            "text": "NOTES: This was entered incorrectly on the source system as a history/journal entry and not as a drug allergy"
          }
        ],
        "assertedDate": "2016-01-08T11:57:34+00:00",
        "category": [
          "medication"
        ],
        "recorder": {
          "reference": "PractitionerRole/e0244de8-07ef-4274-9f7a-d7067bcc8d21"
        },
        "meta": {
          "profile": [
            "https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-AllergyIntolerance-1"
          ]
        }
      }
    }
  ]
}
```