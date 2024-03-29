## {{page-title}}

### Request

Example of a call to return the following items from a patient's structured record:

- Consultations
- Problems
- Medications
- Allergies

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
    },
    {
      "name": "includeMedication",
      "part": [
        {
          "name": "includePrescriptionIssues",
          "valueBoolean": true
        },
        {
          "name": "medicationSearchFromDate",
          "valueDate": "2017-06-04"
        }
      ]
    },
    {
      "name": "includeConsultations",
      "part": [
        {
          "name": "includeNumberOfMostRecent",
          "valuePositiveInt": 3
        }
      ]
    },
    {
      "name": "includeProblems",
      "part": [
        {
          "name": "includeStatus",
          "valueCode": "active"
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
                        },
                        {
                          "url": "DescriptionDisplay",
                          "valueString": "Aspirin 75mg dispersible tablets"
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
                          },
                          {
                            "url": "DescriptionDisplay",
                            "valueString": "O/E - itchy rash"
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
                    },
                    {
                      "url": "DescriptionDisplay",
                      "valueString": "Amoxicillin 250mg capsules"
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
                ]
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
          ]
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
          ]
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
        "title": "Medication List",
        "code": {
          "coding": [
            {
              "code": "933361000000108",
              "display": "Medications and medical devices",
              "system": "http://snomed.info/sct"
            }
          ]
        },
        "subject": {
          "reference": "Patient/04603d77-1a4e-4d63-b246-d7504f8bd833"
        },
        "date": "2018-03-01T10:57:34+00:00",
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
              "reference": "MedicationStatement/6bff710a-0bdc-4c9b-b98b-40db0a107edc"
            }
          },
          {
            "item": {
              "reference": "MedicationStatement/791ceb40-db0a-491d-ab0f-22f5a08509fd"
            }
          }
        ]
      }
    },
    {
      "resource": {
        "resourceType": "MedicationStatement",
        "id": "6bff710a-0bdc-4c9b-b98b-40db0a107edc",
        "meta": {
          "profile": [
            "https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-MedicationStatement-1"
          ]
        },
        "extension": [
          {
            "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-CareConnect-GPC-MedicationStatementLastIssueDate-1",
            "valueDateTime": "2016-05-10"
          },
          {
            "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-CareConnect-GPC-PrescribingAgency-1",
            "valueCodeableConcept": {
              "coding": [
                {
                  "system": "https://fhir.nhs.uk/STU3/CodeSystem/CareConnect-PrescribingAgency-1",
                  "code": "prescribed-at-gp-practice",
                  "display": "Prescribed at GP practice"
                }
              ]
            }
          }
        ],
        "basedOn": [
          {
            "reference": "MedicationRequest/7e68abae-a50a-4dd2-8445-7a2aa9936bee"
          }
        ],
        "status": "completed",
        "medicationReference": {
          "reference": "Medication/c260b451-9821-42de-81f9-ba86dcea2c32"
        },
        "effectiveDateTime": "2016-05-10",
        "dateAsserted": "2016-05-10",
        "subject": {
          "reference": "Patient/04603d77-1a4e-4d63-b246-d7504f8bd833"
        },
        "taken": "unk",
        "note": [
          {
            "text": "Pharmacy Notes: NOTES FOR PHARMACY"
          }
        ],
        "dosage": [
          {
            "patientInstruction": "INSTRUCTIONS FOR PATIENT",
            "text": "TAKE ONE DAILY"
          }
        ]
      }
    },
    {
      "resource": {
        "resourceType": "MedicationStatement",
        "id": "791ceb40-db0a-491d-ab0f-22f5a08509fd",
        "meta": {
          "profile": [
            "https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-MedicationStatement-1"
          ]
        },
        "extension": [
          {
            "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-MedicationStatementLastIssueDate-1",
            "valueDateTime": "2016-09-11"
          },
          {
            "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-CareConnect-GPC-PrescribingAgency-1",
            "valueCodeableConcept": {
              "coding": [
                {
                  "system": "https://fhir.nhs.uk/STU3/CodeSystem/CareConnect-PrescribingAgency-1",
                  "code": "prescribed-at-gp-practice",
                  "display": "Prescribed at GP practice"
                }
              ]
            }
          }
        ],
        "basedOn": [
          {
            "reference": "MedicationRequest/8e078d04-8312-433a-b6b4-46bf52542b0c"
          }
        ],
        "status": "active",
        "medicationReference": {
          "reference": "Medication/8b339981-e9be-4e37-bf03-799295a6aec8"
        },
        "effectivePeriod": {
          "start": "2016-08-11"
        },
        "dateAsserted": "2016-08-11",
        "subject": {
          "reference": "Patient/04603d77-1a4e-4d63-b246-d7504f8bd833"
        },
        "taken": "unk",
        "note": [
          {
            "text": "SOME NOTES"
          }
        ],
        "dosage": [
          {
            "patientInstruction": "INSTRUCTIONS FOR PATIENT",
            "text": "TAKE ONE DAILY"
          }
        ]
      }
    },
    {
      "resource": {
        "resourceType": "MedicationRequest",
        "id": "7e68abae-a50a-4dd2-8445-7a2aa9936bee",
        "meta": {
          "profile": [
            "https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-MedicationRequest-1"
          ]
        },
        "status": "completed",
        "intent": "plan",
        "medicationReference": {
          "reference": "Medication/c260b451-9821-42de-81f9-ba86dcea2c32"
        },
        "subject": {
          "reference": "Patient/04603d77-1a4e-4d63-b246-d7504f8bd833"
        },
        "authoredOn": "2016-05-10",
        "recorder": {
          "reference": "PractitionerRole/e0244de8-07ef-4274-9f7a-d7067bcc8d21"
        },
        "note": [
          {
            "text": "Pharmacy Notes: NOTES FOR PHARMACY"
          }
        ],
        "dosageInstruction": [
          {
            "patientInstruction": "INSTRUCTIONS FOR PATIENT",
            "text": "TAKE ONE DAILY"
          }
        ],
        "dispenseRequest": {
          "expectedSupplyDuration": {
            "code": "d",
            "value": "28",
            "unit": "day",
            "system": "http://unitsofmeasure.org"
          },
          "quantity": {
            "extension": [
              {
                "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-CareConnect-GPC-MedicationQuantityText-1",
                "valueString": "capsule(s)"
              }
            ],
            "value": "28"
          },
          "validityPeriod": {
            "start": "2016-05-10"
          }
        },
        "extension": [
          {
            "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-CareConnect-GPC-PrescriptionType-1",
            "valueCodeableConcept": {
              "coding": [
                {
                  "code": "acute",
                  "display": "Acute",
                  "system": "https://fhir.nhs.uk/STU3/CodeSystem/CareConnect-PrescriptionType-1"
                }
              ]
            }
          }
        ]
      }
    },
    {
      "resource": {
        "resourceType": "MedicationRequest",
        "id": "ca89c863-1569-4e0f-ae8c-31bf98367555",
        "meta": {
          "profile": [
            "https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-MedicationRequest-1"
          ]
        },
        "basedOn": [
          {
            "reference": "MedicationRequest/7e68abae-a50a-4dd2-8445-7a2aa9936bee"
          }
        ],
        "status": "completed",
        "intent": "order",
        "medicationReference": {
          "reference": "Medication/c260b451-9821-42de-81f9-ba86dcea2c32"
        },
        "subject": {
          "reference": "Patient/04603d77-1a4e-4d63-b246-d7504f8bd833"
        },
        "authoredOn": "2016-05-10",
        "recorder": {
          "reference": "PractitionerRole/e0244de8-07ef-4274-9f7a-d7067bcc8d21"
        },
        "note": [
          {
            "text": "NOTES FOR PHARMACY"
          }
        ],
        "dosageInstruction": [
          {
            "patientInstruction": "INSTRUCTIONS FOR PATIENT",
            "text": "TAKE ONE DAILY"
          }
        ],
        "dispenseRequest": {
          "expectedSupplyDuration": {
            "code": [
              "d"
            ],
            "value": "28",
            "unit": "day",
            "system": "http://unitsofmeasure.org"
          },
          "quantity": {
            "extension": [
              {
                "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-CareConnect-GPC-MedicationQuantityText-1",
                "valueString": "capsule(s)"
              }
            ],
            "value": "28"
          },
          "validityPeriod": {
            "start": "2016-05-10"
          }
        },
        "extension": [
          {
            "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-CareConnect-GPC-PrescriptionType-1",
            "valueCodeableConcept": {
              "coding": [
                {
                  "code": "acute",
                  "display": "Acute",
                  "system": "https://fhir.nhs.uk/STU3/CodeSystem/CareConnect-PrescriptionType-1"
                }
              ]
            }
          }
        ]
      }
    },
    {
      "resource": {
        "resourceType": "MedicationRequest",
        "id": "8e078d04-8312-433a-b6b4-46bf52542b0c",
        "meta": {
          "profile": [
            "https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-MedicationRequest-1"
          ]
        },
        "groupIdentifier": {
          "value": "urn:uuid:eba24af1-5b74-4790-aa5a-2134fd27ad75"
        },
        "status": "active",
        "intent": "plan",
        "medicationReference": {
          "reference": "Medication/8b339981-e9be-4e37-bf03-799295a6aec8"
        },
        "subject": {
          "reference": "Patient/04603d77-1a4e-4d63-b246-d7504f8bd833"
        },
        "authoredOn": "2016-08-11",
        "recorder": {
          "reference": "PractitionerRole/e0244de8-07ef-4274-9f7a-d7067bcc8d21"
        },
        "note": [
          {
            "text": "NOTES FOR PHARMACY"
          }
        ],
        "dosageInstruction": [
          {
            "patientInstruction": "INSTRUCTIONS FOR PATIENT",
            "text": "TAKE ONE 3 TIMES/DAY"
          }
        ],
        "dispenseRequest": {
          "expectedSupplyDuration": {
            "code": [
              "d"
            ],
            "value": "28",
            "unit": "day",
            "system": "http://unitsofmeasure.org"
          },
          "quantity": {
            "extension": [
              {
                "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-CareConnect-GPC-MedicationQuantityText-1",
                "valueString": "tablets(s)"
              }
            ],
            "value": "84"
          },
          "validityPeriod": {
            "start": "2016-08-11"
          }
        },
        "extension": [
          {
            "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-CareConnect-GPC-MedicationRepeatInformation-1",
            "extension": [
              {
                "url": "numberOfRepeatPrescriptionsAllowed",
                "valuePositiveInt": 5
              },
              {
                "url": "numberOfRepeatPrescriptionsIssued",
                "valuePositiveInt": 2
              }
            ]
          },
          {
            "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-CareConnect-GPC-PrescriptionType-1",
            "valueCodeableConcept": {
              "coding": [
                {
                  "code": "repeat",
                  "display": "Repeat",
                  "system": "https://fhir.nhs.uk/STU3/CodeSystem/CareConnect-PrescriptionType-1"
                }
              ]
            }
          }
        ]
      }
    },
    {
      "resource": {
        "resourceType": "MedicationRequest",
        "id": "8afe3af9-995d-4ccc-9211-f8c2620be670",
        "meta": {
          "profile": [
            "https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-MedicationRequest-1"
          ]
        },
        "basedOn": [
          {
            "reference": "MedicationRequest/8e078d04-8312-433a-b6b4-46bf52542b0c"
          }
        ],
        "groupIdentifier": {
          "value": "urn:uuid:eba24af1-5b74-4790-aa5a-2134fd27ad75"
        },
        "status": "completed",
        "intent": "order",
        "medicationReference": {
          "reference": "Medication/8b339981-e9be-4e37-bf03-799295a6aec8"
        },
        "subject": {
          "reference": "Patient/04603d77-1a4e-4d63-b246-d7504f8bd833"
        },
        "authoredOn": "2016-08-11",
        "recorder": {
          "reference": "PractitionerRole/e0244de8-07ef-4274-9f7a-d7067bcc8d21"
        },
        "note": [
          {
            "text": "NOTES FOR PHARMACY"
          }
        ],
        "dosageInstruction": [
          {
            "patientInstruction": "INSTRUCTIONS FOR PATIENT",
            "text": "TAKE ONE 3 TIMES/DAY"
          }
        ],
        "dispenseRequest": {
          "expectedSupplyDuration": {
            "code": [
              "d"
            ],
            "value": "28",
            "unit": "day",
            "system": "http://unitsofmeasure.org"
          },
          "quantity": {
            "extension": [
              {
                "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-CareConnect-GPC-MedicationQuantityText-1",
                "valueString": "tablet(s)"
              }
            ],
            "value": "84"
          },
          "validityPeriod": {
            "start": "2016-08-11"
          }
        },
        "extension": [
          {
            "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-CareConnect-GPC-PrescriptionType-1",
            "valueCodeableConcept": {
              "coding": [
                {
                  "code": "repeat",
                  "display": "Repeat",
                  "system": "https://fhir.nhs.uk/STU3/CodeSystem/CareConnect-PrescriptionType-1"
                }
              ]
            }
          }
        ]
      }
    },
    {
      "resource": {
        "resourceType": "MedicationRequest",
        "id": "a946012a-283b-46c4-8312-e1312a54ab9c",
        "meta": {
          "profile": [
            "https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-MedicationRequest-1"
          ]
        },
        "basedOn": [
          {
            "reference": "MedicationRequest/8e078d04-8312-433a-b6b4-46bf52542b0c"
          }
        ],
        "groupIdentifier": {
          "value": "urn:uuid:eba24af1-5b74-4790-aa5a-2134fd27ad75"
        },
        "status": "completed",
        "intent": "order",
        "medicationReference": {
          "reference": "Medication/8b339981-e9be-4e37-bf03-799295a6aec8"
        },
        "subject": {
          "reference": "Patient/04603d77-1a4e-4d63-b246-d7504f8bd833"
        },
        "authoredOn": "2016-09-11",
        "recorder": {
          "reference": "PractitionerRole/e0244de8-07ef-4274-9f7a-d7067bcc8d21"
        },
        "note": [
          {
            "text": "NOTES FOR PHARMACY"
          }
        ],
        "dosageInstruction": [
          {
            "patientInstruction": "INSTRUCTIONS FOR PATIENT",
            "text": "TAKE ONE 3 TIMES/DAY"
          }
        ],
        "dispenseRequest": {
          "expectedSupplyDuration": {
            "code": [
              "d"
            ],
            "value": "28",
            "unit": "day",
            "system": "http://unitsofmeasure.org"
          },
          "quantity": {
            "extension": [
              {
                "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-CareConnect-GPC-MedicationQuantityText-1",
                "valueString": "tablet(s)"
              }
            ],
            "value": "84"
          },
          "validityPeriod": {
            "start": "2016-09-11"
          }
        },
        "extension": [
          {
            "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-CareConnect-GPC-PrescriptionType-1",
            "valueCodeableConcept": {
              "coding": [
                {
                  "code": "repeat",
                  "display": "Repeat",
                  "system": "https://fhir.nhs.uk/STU3/CodeSystem/CareConnect-PrescriptionType-1"
                }
              ]
            }
          }
        ]
      }
    },
    {
      "resource": {
        "resourceType": "Medication",
        "meta": {
          "profile": [
            "https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Medication-1"
          ]
        },
        "id": "c260b451-9821-42de-81f9-ba86dcea2c32",
        "code": {
          "coding": [
            {
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
              ],
              "display": "Amoxicillin 250mg capsules",
              "code": "323509004",
              "system": "http://snomed.info/sct"
            }
          ]
        }
      }
    },
    {
      "resource": {
        "resourceType": "Medication",
        "id": "8b339981-e9be-4e37-bf03-799295a6aec8",
        "meta": {
          "profile": [
            "https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Medication-1"
          ]
        },
        "code": {
          "coding": [
            {
              "extension": [
                {
                  "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
                  "extension": [
                    {
                      "url": "DescriptionID",
                      "valueId": "462888013"
                    },
                    {
                      "url": "DescriptionDisplay",
                      "valueString": "Aspirin 75mg dispersible tablet"
                    }
                  ]
                }
              ],
              "display": "Aspirin 75mg dispersible tablets",
              "code": "319773006",
              "system": "http://snomed.info/sct"
            }
          ]
        }
      }
    },
    {
      "resource": {
        "resourceType": "OperationOutcome",
        "id": "8b679981-e9be-4e37-b103-799295a6aec8",
        "meta": {
          "profile": [
            "https://fhir.nhs.uk/STU3/StructureDefinition/GPConnect-OperationOutcome-1"
          ]
        },
        "issue": [
          {
            "severity": "warning",
            "code": "not-supported",
            "details": {
              "coding": [
                {
                  "system": "https://fhir.nhs.uk/STU3/CodeSystem/Spine-ErrorOrWarningCode-1",
                  "code": "NOT_IMPLEMENTED",
                  "display": "Not implemented"
                }
              ],
              "text": "includeConsultations is an unrecognised parameter"
            },
            "diagnostics": "includeConsultations"
          },
          {
            "severity": "warning",
            "code": "not-supported",
            "details": {
              "coding": [
                {
                  "system": "https://fhir.nhs.uk/STU3/CodeSystem/Spine-ErrorOrWarningCode-1",
                  "code": "NOT_IMPLEMENTED",
                  "display": "Not implemented"
                }
              ],
              "text": "includeProblems is an unrecognised parameter"
            },
            "diagnostics": "includeProblems"
          }
        ]
      }
    }
  ]
}
```

Note the inclusion of an OperationOutcome with two issues about the unsupported parameters, includeConsultations and includeProblems.