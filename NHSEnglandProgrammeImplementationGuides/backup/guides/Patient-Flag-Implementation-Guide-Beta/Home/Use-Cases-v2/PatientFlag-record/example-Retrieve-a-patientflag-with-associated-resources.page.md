# Retrieve PatientFlag by Type and Details

:::info
This page explains how a Practitioner retrieves a specific type of PatientFlag (e.g., Reasonable Adjustment flag) along with all associated Additional Detail resources using both patient and code parameters.
:::

## 📘 Overview

This use case focuses on retrieving a PatientFlag record **of a specific type** using the `code` search parameter alongside the patient's NHSNumber.

For full context, see [Home](Home).

> 💡 Note: The standard FHIR `Flag` resource doesn't support searching by `code`. However, the `PatientFlag` used here is based on a custom profile with an extended search parameter:{{pagelink:Home/FHIR-Assets/Profiles/England-Flag-Patient-Flag.page.md}} and its associated {{pagelink:Home/FHIR-Assets/SearchParameters/England-FlagCode.page.md}}.


## 🩺 Use Case

A Practitioner searches for a specific type of flag (e.g., "Reasonable Adjustment") for a patient, and the API returns the relevant `PatientFlag` resource **plus** any linked `Additional Detail` resources.

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
</plantuml>`


## 📋 User Story

> **As a Practitioner**, I want to search for PatientFlag records of a specific type for a given patient, so that I can review both the flag and its associated context (Additional Detail resources).


## 👥 Actors

| Actor                        | Description                                                        |
|-----------------------------|--------------------------------------------------------------------|
| **Practitioner**            | The clinician initiating the query                                 |
| **PatientFlag FHIR API**    | API used to query flag and detail resources                        |
| **FHIR Repository**         | Backend system holding PatientFlag and Additional Detail resources |


## ⚙️ Workflow

### Frequency of Use
- As needed

### Trigger
- Practitioner seeks information related to a specific flag type (e.g., Reasonable Adjustment).

### Pre-conditions
- Practitioner knows the patient's NHSNumber and the flag `code`.
- Practitioner has proper access rights.

### Post-conditions
- Practitioner receives the specific flag and related details or a response indicating none found.


## 🔄 Flow

### Main Flow

1. Practitioner queries `PatientFlag` API using `patient` and `code` search parameters.
2. API queries the FHIR repository for the relevant `PatientFlag`.
3. API retrieves and aggregates associated Additional Detail resources.
4. API returns all matched resources in a single `Bundle` to the Practitioner.

### Alternate Flow

| Step | Condition                        | Outcome                                                |
|------|----------------------------------|--------------------------------------------------------|
| 3a   | No `PatientFlag` found           | Return an empty searchset `Bundle`                     |
| 3b   | Invalid patient or flag `code`   | Return an `OperationOutcome` with `not-found` error    |

## 🧩 System Interaction

<plantuml>
@startuml

skinparam actorStyle hollow

actor        "Practitioner"     as pra
boundary     "FHIR API"         as api
entity       "Patient Flag"     as pfg
entity       "Additional Detail"  as add

pra ->  api : Query for record
api ->  pfg : Query for record
api <-- pfg : SearchSet Bundle
opt
  loop for each Additional Detail resource type
  api ->  add : Query for records
  api <-- add : SearchSet Bundle
  end
end
pra <-- api : SearchSet Bundle
pra <-- api : OperationOutcome

@enduml
</plantuml>

## 🔍 Querying the API

Use this query format:

```
GET [baseUrl]/PatientFlag?patient=[NHSNumber]&code=[flagCode]
```

### Example:

```
GET [baseUrl]/PatientFlag?patient=9449306753&code=NRAF
```

Returns the `PatientFlag` for patient `9449306753` of type `NRAF` (Reasonable Adjustment), plus any Additional Detail resources.

> 🔎 Uses custom search parameter defined in {{pagelink:Home/FHIR-Assets/SearchParameters/England-FlagCode.page.md}} .

---

## ✅ Response Examples

### 🟢 Successful Response

```json
{
  "resourceType": "Bundle",
  "id": "RA-FlagCondition-Example",
  "type": "searchset",
  "total": 3,
  "link": [
    {
      "relation": "self",
      "url": "https://fhir.example.org/FlagCondition?subject=Patient/PatientFlag-AlanMann-Example"
    }
  ],
  "entry": [
    {
      "fullUrl": "urn:uuid:22345678-1234-5678-1234-567812345678",
      "resource": {
        "resourceType": "Flag",
        "id": "RA-PatientFlag-Example",
        "meta": {
          "profile": ["https://fhir.nhs.uk/England/StructureDefinition/England-Flag-PatientFlag"]
        },
        "extension": [
          {
            "url": "http://hl7.org/fhir/StructureDefinition/flag-detail",
            "valueReference": {
              "reference": "urn:uuid:42345678-1234-5678-1234-567812345678",
              "type": "Condition"
            }
          },
          {
            "url": "http://hl7.org/fhir/StructureDefinition/flag-detail",
            "valueReference": {
              "reference": "urn:uuid:12345678-1234-5678-1234-567812345678",
              "type": "Flag"
            }
          },
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
      "fullUrl": "urn:uuid:12345678-1234-5678-1234-567812345678",
      "resource": {
        "resourceType": "Flag",
        "id": "RA-Flag-Example",
        "meta": {
          "profile": ["https://fhir.nhs.uk/England/StructureDefinition/England-Flag-PatientFlag-Adjustment"]
        },
        "contained": [
          {
            "resourceType": "Provenance",
            "id": "873a38eb-0f9c-4a66-a4e9-8e4be2350d6b",
            "meta": {
              "profile": ["https://fhir.nhs.uk/England/StructureDefinition/England-Provenance-Flag"]
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
                "role": {
                  "coding": [
                    {
                      "system": "https://fhir.hl7.org.uk/STU3/CodeSystem/CareConnect-SDSJobRoleName-1",
                      "code": "R0260",
                      "display": "General Medical Practitioner"
                    }
                  ]
                },
                "who": {
                  "reference": "Practitioner/2ee4tr6a9"
                },
                "onBehalfOf": {
                  "reference": "Organization/a3e5i7"
                }
              }
            ]
          }
        ],
        "extension": [
          {
            "url": "https://fhir.nhs.uk/England/StructureDefinition/Extension-FlagNotes",
            "valueAnnotation": {
              "text": "Example of flag notes extension text in adjustment flag"
            }
          }
        ],
        "status": "active",
        "category": [
          {
            "coding": [
              {
                "system": "https://fhir.nhs.uk/England/CodeSystem/England-FlagCategoryPatient",
                "code": "national-reasonable-adjustment-flag",
                "display": "National Reasonable Adjustments Flag"
              }
            ]
          },
          {
            "coding": [
              {
                "system": "https://fhir.nhs.uk/England/CodeSystem/England-FlagCategoryRA",
                "code": "communication-support",
                "display": "Communication support"
              }
            ]
          }
        ],
        "code": {
          "coding": [
            {
              "system": "https://snomed.info/sct",
              "code": "1082681000000103",
              "display": "Requires support for receptive communication needs"
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
        "resourceType": "Condition",
        "id": "RA-Condition-Example",
        "meta": {
          "profile": ["https://fhir.nhs.uk/England/StructureDefinition/England-Condition-Flag"]
        },
        "contained": [
          {
            "resourceType": "Provenance",
            "id": "6a6b18a7-c077-49da-929f-a8dd38468f79",
            "meta": {
              "profile": ["https://fhir.nhs.uk/England/StructureDefinition/England-Provenance-Flag"]
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
                "role": {
                  "coding": [
                    {
                      "system": "https://fhir.hl7.org.uk/STU3/CodeSystem/CareConnect-SDSJobRoleName-1",
                      "code": "R0260",
                      "display": "General Medical Practitioner"
                    }
                  ]
                },
                "who": {
                  "reference": "Practitioner/2ee4tr6a9"
                },
                "onBehalfOf": {
                  "reference": "Organization/a3e5i7"
                }
              }
            ]
          }
        ],
        "clinicalStatus": {
          "coding": [
            {
              "system": "http://terminology.hl7.org/CodeSystem/condition-clinical",
              "code": "active"
            }
          ]
        },
        "category": [
          {
            "coding": [
              {
                "system": "https://fhir.nhs.uk/England/CodeSystem/England-FlagCategoryPatient",
                "code": "national-reasonable-adjustment-flag",
                "display": "National Reasonable Adjustments Flag"
              }
            ]
          },
          {
            "coding": [
              {
                "system": "https://fhir.nhs.uk/England/CodeSystem/England-ConditionCategoryRA",
                "code": "issue",
                "display": "Issue"
              }
            ]
          }
        ],
        "code": {
          "coding": [
            {
              "system": "https://fhir.nhs.uk/England/CodeSystem/England-ConditionCodeRA",
              "code": "learning",
              "display": "Learning or understanding or concentrating"
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
    }
  ]
}

```

### ⚪ No Records Found

```json
{
  "resourceType": "Bundle",
  "type": "searchset",
  "total": 0,
  "entry": []
}
```

### 🔴 Error: Invalid Patient or Code

```json
{
  "resourceType": "OperationOutcome",
  "issue": [
    {
      "severity": "error",
      "code": "not-found",
      "diagnostics": "No PatientFlag found for given patient and code"
    }
  ]
}
```

## 🔐 Security and Access

- OAuth2 scopes required: `patient/PatientFlag.read`
- Role-based access is enforced.
- Access logging is enabled for audit.

## 📎 Notes

- Custom search param support must be enabled in FHIR server.
- Supports returning a mix of Flag and Additional Detail resources in one `Bundle`.

---
