# Retrieve PatientFlags

:::info
This page describes how a Practitioner retrieves Patient Flag records for a given patient using their NHSNumber via the `PatientFlag` FHIR API.
:::

## 📘 Overview

Patient Flags are clinical markers that provide important information about a patient. They can include alerts such as allergies, safeguarding issues, or specific care instructions.

For system-level context, see [Home](Home).

## 🩺 Use Case

A Practitioner retrieves a patient's flag records by querying the `PatientFlag` endpoint using the patient's NHSNumber.

### Use Case Diagram
<plantuml>
@startuml

skinparam actorStyle awesome
left to right direction

rectangle "Patient Flag"{
actor Practitioner as pra
usecase "Research" as res <<abstract>>
usecase "Retrieve Patient Flag record" as ret <<abstract>>
}

pra -- res
res <.. ret : include

@enduml
</plantuml>

## 📋 User Story

> **As a Practitioner**, I want to retrieve PatientFlag records using a patient's NHSNumber, so that I can be alerted to any critical clinical information when making care decisions.


## 👥 Actors

| Actor                        | Description                                                |
|-----------------------------|------------------------------------------------------------|
| **Practitioner**            | Clinician accessing the system                             |
| **PatientFlag FHIR API**    | API endpoint exposing `PatientFlag` resources              |
| **FHIR Repository**         | Backend data store containing flag records                 |

## ⚙️ Workflow

### Frequency of Use
- As needed

### Trigger
- Practitioner initiates a request to view flags for a patient.

### Pre-conditions
- Practitioner knows the patient's NHSNumber or sufficient details.
- Practitioner is authorized to access this data.

### Post-conditions
- Practitioner receives relevant flag data or confirmation that none exists.

## 🔄 Flow

### Main Flow

1. Practitioner sends query to `PatientFlag` API using patient’s NHSNumber.
2. API forwards the query to the FHIR repository.
3. Repository returns matching PatientFlag records.
4. API sends the result back to the Practitioner in a searchset bundle.

### Alternate Flow

| Step | Condition                                 | Outcome                                              |
|------|-------------------------------------------|------------------------------------------------------|
| 3a   | No flags found                             | Return empty `Bundle` with `total: 0`                |
| 3b   | NHSNumber not found                        | Return `OperationOutcome` with `not-found` issue     |

## 🧩 System Interaction

<plantuml>
@startuml

skinparam actorStyle hollow

actor        "Practitioner"     as pra
boundary     "FHIR API"         as api
entity       "Patient Flag"     as pfg

pra ->  api : Query for records
api ->  pfg : Query for records
api <-- pfg : SearchSet Bundle
pra <-- api : SearchSet Bundle
pra <-- api : OperationOutcome

@enduml
</plantuml>


## 🔍 Querying the API

Use the FHIR Search API to retrieve `PatientFlag` resources.

### Example Query

```http
GET [baseUrl]/PatientFlag?patient=9449306753
```

This retrieves all `PatientFlag` resources for the patient with NHSNumber `9449306753`.

> ℹ️ Uses [`Flag.patient`](http://www.hl7.org/fhir/R4/flag.html#search) search parameter.

## ✅ Response Examples

### 🟢 Successful Response

```json
{
  "resourceType": "Bundle",
  "id": "PatientFlag-Bundle-Example",
  "type": "searchset",
  "total": 3,
  "link": [
    {
      "relation": "self",
      "url": "https://fhirserver.example.org/Flag?patient=PatientFlag-AlanMann-Example"
    }
  ],
  "entry": [
    {
      "fullUrl": "urn:uuid:82345678-1234-5678-1234-567812345678",
      "resource": {
        "resourceType": "Flag",
        "id": "RA-PatientFlag-Example",
        "meta": {
          "profile": [
            "https://fhir.nhs.uk/England/StructureDefinition/England-Flag-PatientFlag"
          ]
        },
        "contained": [
          {
            "resourceType": "Provenance",
            "id": "c4e2e862-3bf4-4176-a186-9f1732938260",
            "meta": {
              "profile": [
                "https://fhir.nhs.uk/England/StructureDefinition/England-Provenance-Flag"
              ]
            },
            "target": [
              {
                "reference": "#"
              }
            ],
            "recorded": "2024-01-01T11:00:00+00:00",
            "activity": {
              "coding": [
                {
                  "system": "http://terminology.hl7.org/CodeSystem/v3-DataOperation",
                  "code": "CREATE",
                  "display": "create"
                }
              ]
            },
            "agent": [
              {
                "role": [
                  {
                    "coding": [
                      {
                        "system": "https://fhir.hl7.org.uk/STU3/CodeSystem/CareConnect-SDSJobRoleName-1",
                        "code": "R0260",
                        "display": "General Medical Practitioner"
                      }
                    ]
                  }
                ],
                "who": {
                  "reference": "https://sds.spineservices.nhs.uk/Practitioner/2ee4tr6a9"
                },
                "onBehalfOf": {
                  "reference": "https://directory.spineservices.nhs.uk/Organization/a3e5i7"
                }
              }
            ]
          }
        ],
        "extension": [
          {
            "url": "https://fhir.nhs.uk/England/StructureDefinition/Extension-FlagNotes",
            "valueAnnotation": {
              "text": "Example of flag notes extension text in patient flag"
            }
          }
        ],
        "status": "active",
        "code": {
          "coding": [
            {
              "system": "https://fhir.nhs.uk/England/CodeSystem/England-FlagCategoryPatient",
              "code": "national-reasonable-adjustment-flag",
              "display": "National Reasonable Adjustments Flag"
            }
          ]
        },
        "subject": {
          "reference": "Patient/PatientFlag-AlanMann-Example"
        }
      },
      "search": {
        "mode": "match"
      }
    },
    {
      "fullUrl": "urn:uuid:32345678-1234-5678-1234-567812345678",
      "resource": {
        "resourceType": "Flag",
        "id": "FGM-PatientFlag-Example",
        "meta": {
          "profile": [
            "https://fhir.nhs.uk/England/StructureDefinition/England-Flag-PatientFlag"
          ]
        },
        "contained": [
          {
            "resourceType": "Provenance",
            "id": "3fc83fd8-4a6d-48e4-91ab-12bb10a4a834",
            "meta": {
              "profile": [
                "https://fhir.nhs.uk/England/StructureDefinition/England-Provenance-Flag"
              ]
            },
            "target": [
              {
                "reference": "#"
              }
            ],
            "recorded": "2024-01-01T11:00:00+00:00",
            "activity": {
              "coding": [
                {
                  "system": "http://terminology.hl7.org/CodeSystem/v3-DataOperation",
                  "code": "CREATE",
                  "display": "create"
                }
              ]
            },
            "agent": [
              {
                "role": [
                  {
                    "coding": [
                      {
                        "system": "https://fhir.hl7.org.uk/STU3/CodeSystem/CareConnect-SDSJobRoleName-1",
                        "code": "R0260",
                        "display": "General Medical Practitioner"
                      }
                    ]
                  }
                ],
                "who": {
                  "reference": "https://sds.spineservices.nhs.uk/Practitioner/2ee4tr6a9"
                },
                "onBehalfOf": {
                  "reference": "https://directory.spineservices.nhs.uk/Organization/a3e5i7"
                }
              }
            ]
          }
        ],
        "extension": [
          {
            "url": "https://fhir.nhs.uk/England/StructureDefinition/Extension-FlagNotes",
            "valueAnnotation": {
              "text": "Example of flag notes extension text in patient flag"
            }
          }
        ],
        "status": "active",
        "code": {
          "coding": [
            {
              "system": "https://fhir.nhs.uk/England/CodeSystem/England-FlagCategoryPatient",
              "code": "female-genital-mutilation-flag",
              "display": "Female Genital Mutilation Flag"
            }
          ]
        },
        "subject": {
          "reference": "Patient/PatientFlag-AlanMann-Example"
        }
      },
      "search": {
        "mode": "match"
      }
    },
    {
      "fullUrl": "urn:uuid:42345678-1234-5678-1234-567812345678",
      "resource": {
        "resourceType": "Flag",
        "id": "CPIS-Flag-Example",
        "meta": {
          "profile": [
            "https://fhir.nhs.uk/England/StructureDefinition/England-Flag-PatientFlag"
          ]
        },
        "contained": [
          {
            "resourceType": "Provenance",
            "id": "1fc83fd8-4a6d-48e4-91ab-12bb10a4a834",
            "meta": {
              "profile": [
                "https://fhir.nhs.uk/England/StructureDefinition/England-Provenance-Flag"
              ]
            },
            "target": [
              {
                "reference": "#"
              }
            ],
            "recorded": "2024-07-22T09:00:00+00:00",
            "activity": {
              "coding": [
                {
                  "system": "http://terminology.hl7.org/CodeSystem/v3-DataOperation",
                  "code": "CREATE",
                  "display": "create"
                }
              ]
            },
            "agent": [
              {
                "role": [
                  {
                    "coding": [
                      {
                        "system": "https://fhir.hl7.org.uk/STU3/CodeSystem/CareConnect-SDSJobRoleName-1",
                        "code": "R0260",
                        "display": "General Medical Practitioner"
                      }
                    ]
                  }
                ],
                "who": {
                  "reference": "https://sds.spineservices.nhs.uk/Practitioner/2ee4tr6a9"
                },
                "onBehalfOf": {
                  "reference": "https://directory.spineservices.nhs.uk/Organization/a3e5i7"
                }
              }
            ]
          }
        ],
        "extension": [
          {
            "url": "http://hl7.org/fhir/StructureDefinition/flag-detail",
            "valueReference": {
              "reference": "CarePlan/CPIS-CarePlan-example",
              "display": "Child Protection Plan for Alan Mann"
            }
          }
        ],
        "status": "active",*
        
        "code": {
          "coding": [
            {
              "system": "https://fhir.nhs.uk/England/CodeSystem/England-FlagCategoryPatient",
              "code": "child-protection-information-system-flag",
              "display": "Child Protection Information System Flag"
            }
          ]
        },
        "subject": {
          "reference": "Patient/PatientFlag-AlanMann-Example",
          "display": "Alan Mann"
        },
        "period": {
          "start": "2024-07-22T09:00:00+00:00"
        }
      },
      "search": {
        "mode": "match"
      }
    }
  ]
}

```

### ⚪ No Flags Found

```json
{
  "resourceType": "Bundle",
  "type": "searchset",
  "total": 0,
  "entry": []
}
```

### 🔴 Error: Patient Not Found

```json
{
  "resourceType": "OperationOutcome",
  "issue": [
    {
      "severity": "error",
      "code": "not-found",
      "diagnostics": "No patient found with identifier 9449306753"
    }
  ]
}
```

---

## 🔐 Security and Access

- Access requires proper authentication and authorization.
- All API accesses are logged for auditing.

---
