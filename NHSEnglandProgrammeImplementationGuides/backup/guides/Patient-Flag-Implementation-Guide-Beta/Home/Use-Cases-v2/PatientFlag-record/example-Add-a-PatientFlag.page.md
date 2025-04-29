# Record PatientFlags

:::info
This page describes how a Practitioner records Patient Flag information for a given patient using the `PatientFlag` FHIR API.
:::

## 📘 Overview

Patient Flags are clinical markers used to highlight significant information about a patient such as allergies, safeguarding concerns, or communication needs.

For system-level context, see [Home](Home).


## 🩺 Use Case

A Practitioner records a patient's flag record by submitting a new Flag resource to the `PatientFlag` endpoint.

### Use Case Diagram

<plantuml>
@startuml

skinparam actorStyle awesome
left to right direction

rectangle "Patient Flag"{
actor Practitioner as pra
usecase "Record" as record <<abstract>>
usecase "Add Patient Flag record" as add <<abstract>>
}


actor Patient as pat

usecase "Consult" as consult <<abstract>>

pat -- consult
pra -- consult
pra -- record
record <.. add : include

@enduml
</plantuml>

## 📋 User Story

> **As a Practitioner**, I want to record PatientFlag information for a patient, so that others are alerted to any relevant clinical considerations.

## 👥 Actors

| Actor                        | Description                                                |
|-----------------------------|------------------------------------------------------------|
| **Practitioner**            | Clinician recording the flag                               |
| **PatientFlag FHIR API**    | API endpoint accepting new `PatientFlag` resources         |
| **FHIR Repository**         | Backend data store containing flag records                 |

## ⚙️ Workflow

### Frequency of Use
- As needed

### Trigger
- Practitioner identifies a need to flag important information for a patient.

### Pre-conditions
- Practitioner is authorized to create or update PatientFlag records.

### Post-conditions
- PatientFlag is recorded and available for future retrieval.

## 🔄 Flow

### Main Flow

1. Practitioner initiates a POST request to the `PatientFlag` endpoint.
2. API validates and stores the resource in the FHIR repository.
3. API returns a confirmation of success or failure.

### Alternate Flow

| Step | Condition                              | Outcome                                              |
|------|----------------------------------------|------------------------------------------------------|
| 2a   | Validation fails                        | Return `OperationOutcome` with validation errors     |
| 2b   | Record already exists with same flag type | Merge notes and update existing resource             |

## 🧩 System Interaction

<plantuml>
@startuml

skinparam actorStyle hollow

actor        "Patient"          as pat
actor        "Practitioner"     as pra
boundary     "FHIR API"         as api
entity       "Patient Flag"     as flg

pra ->  pat : Consult patient
pra ->  api : Record adjustment record

api ->  flg : Create/update resource
flg ->  flg : Validate
api <-- flg : return
alt Validation failed
  api -> api : rollback
end

pra <-- api : OperationOutcome

@enduml
</plantuml>

## 🔍 Posting the Resource

Use the FHIR create endpoint to submit a new `PatientFlag` resource.

### Example Request

```
POST [baseURL]/PatientFlag
```

```json
{
  "resourceType": "Bundle",
  "id": "AddRARecordTransaction-Bundle-Example",
  "type": "transaction",
  "entry": [
    {
      "fullUrl": "Condition/RA-Condition-Example",
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
            "target": [{ "reference": "#" }],
            "recorded": "2024-01-01T11:00:00+00:00",
            "activity": {
              "coding": [{
                "system": "http://terminology.hl7.org/CodeSystem/v3-DataOperation",
                "code": "CREATE",
                "display": "create"
              }]
            },
            "agent": [{
              "role": {
                "coding": [{
                  "system": "https://fhir.hl7.org.uk/STU3/CodeSystem/CareConnect-SDSJobRoleName-1",
                  "code": "R0260",
                  "display": "General Medical Practitioner"
                }]
              },
              "who": {
                "reference": "https://sds.spineservices.nhs.uk/Practitioner/2ee4tr6a9"
              },
              "onBehalfOf": {
                "reference": "https://directory.spineservices.nhs.uk/Organization/a3e5i7"
              }
            }]
          }
        ],
        "clinicalStatus": {
          "coding": [{
            "system": "http://terminology.hl7.org/CodeSystem/condition-clinical",
            "code": "active"
          }]
        },
        "category": [
          {
            "coding": [{
              "system": "https://fhir.nhs.uk/England/CodeSystem/England-FlagCategoryPatient",
              "code": "national-reasonable-adjustment-flag",
              "display": "National Reasonable Adjustments Flag"
            }]
          },
          {
            "coding": [{
              "system": "https://fhir.nhs.uk/England/CodeSystem/England-ConditionCategoryRA",
              "code": "issue",
              "display": "Issue"
            }]
          }
        ],
        "code": {
          "coding": [{
            "system": "https://fhir.nhs.uk/England/CodeSystem/England-ConditionCodeRA",
            "code": "learning",
            "display": "Learning or understanding or concentrating"
          }]
        },
        "subject": {
          "reference": "Patient/PatientFlag-AlanMann-Example"
        }
      },
      "request": {
        "method": "POST",
        "url": "Condition/RA-Condition-Example"
      }
    },
    {
      "fullUrl": "Flag/RA-PatientFlag-Example",
      "resource": {
        "resourceType": "Flag",
        "id": "RA-PatientFlag-Example",
        "meta": {
          "profile": ["https://fhir.nhs.uk/England/StructureDefinition/England-Flag-PatientFlag"]
        },
        "contained": [
          {
            "resourceType": "Provenance",
            "id": "c4e2e862-3bf4-4176-a186-9f1732938260",
            "meta": {
              "profile": ["https://fhir.nhs.uk/England/StructureDefinition/England-Provenance-Flag"]
            },
            "target": [{ "reference": "#" }],
            "recorded": "2024-01-01T11:00:00+00:00",
            "activity": {
              "coding": [{
                "system": "http://terminology.hl7.org/CodeSystem/v3-DataOperation",
                "code": "CREATE",
                "display": "create"
              }]
            },
            "agent": [{
              "role": {
                "coding": [{
                  "system": "https://fhir.hl7.org.uk/STU3/CodeSystem/CareConnect-SDSJobRoleName-1",
                  "code": "R0260",
                  "display": "General Medical Practitioner"
                }]
              },
              "who": {
                "reference": "https://sds.spineservices.nhs.uk/Practitioner/2ee4tr6a9"
              },
              "onBehalfOf": {
                "reference": "https://directory.spineservices.nhs.uk/Organization/a3e5i7"
              }
            }]
          }
        ],
        "extension": [
          {
            "url": "https://fhir.nhs.uk/England/StructureDefinition/Extension-FlagNotes",
            "valueAnnotation": {
              "text": "Example of flag notes extension text in patient flag"
            }
          },
          {
            "url": "http://hl7.org/fhir/StructureDefinition/flag-detail",
            "valueReference": {
              "reference": "Condition/RA-Condition-Example",
              "type": "Condition"
            }
          },
          {
            "url": "http://hl7.org/fhir/StructureDefinition/flag-detail",
            "valueReference": {
              "reference": "Flag/RA-Flag-Example",
              "type": "Flag"
            }
          }
        ],
        "status": "active",
        "code": {
          "coding": [{
            "system": "https://fhir.nhs.uk/England/CodeSystem/England-FlagCategoryPatient",
            "code": "national-reasonable-adjustment-flag",
            "display": "National Reasonable Adjustments Flag"
          }]
        },
        "subject": {
          "reference": "Patient/PatientFlag-AlanMann-Example"
        }
      },
      "request": {
        "method": "POST",
        "url": "Flag/RA-PatientFlag-Example"
      }
    },
    {
      "fullUrl": "Flag/RA-Flag-Example",
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
            "target": [{ "reference": "#" }],
            "recorded": "2024-01-01T11:00:00+00:00",
            "activity": {
              "coding": [{
                "system": "http://terminology.hl7.org/CodeSystem/v3-DataOperation",
                "code": "CREATE",
                "display": "create"
              }]
            },
            "agent": [{
              "role": {
                "coding": [{
                  "system": "https://fhir.hl7.org.uk/STU3/CodeSystem/CareConnect-SDSJobRoleName-1",
                  "code": "R0260",
                  "display": "General Medical Practitioner"
                }]
              },
              "who": {
                "reference": "https://sds.spineservices.nhs.uk/Practitioner/2ee4tr6a9"
              },
              "onBehalfOf": {
                "reference": "https://directory.spineservices.nhs.uk/Organization/a3e5i7"
              }
            }]
          }
        ],
        "extension": [{
          "url": "https://fhir.nhs.uk/England/StructureDefinition/Extension-FlagNotes",
          "valueAnnotation": {
            "text": "Example of flag notes extension text in adjustment flag"
          }
        }],
        "status": "active",
        "category": [
          {
            "coding": [{
              "system": "https://fhir.nhs.uk/England/CodeSystem/England-FlagCategoryPatient",
              "code": "national-reasonable-adjustment-flag",
              "display": "National Reasonable Adjustments Flag"
            }]
          },
          {
            "coding": [{
              "system": "https://fhir.nhs.uk/England/CodeSystem/England-FlagCategoryRA",
              "code": "communication-support",
              "display": "Communication support"
            }]
          }
        ],
        "code": {
          "coding": [{
            "system": "https://snomed.info/sct",
            "code": "1082681000000103",
            "display": "Requires support for receptive communication needs"
          }]
        },
        "subject": {
          "reference": "Patient/PatientFlag-AlanMann-Example"
        }
      },
      "request": {
        "method": "POST",
        "url": "Flag/RA-Flag-Example"
      }
    }
  ]
}

```

## ✅ Response Examples

### 🟢 Successful Creation

```json
{
  "resourceType": "Flag",
  "id": "new-flag-id",
  "status": "active"
}
```

### 🔴 Error: Validation Failure

```json
{
  "resourceType": "OperationOutcome",
  "issue": [
    {
      "severity": "error",
      "code": "invalid",
      "diagnostics": "Missing required extension"
    }
  ]
}
```

---

## 🔐 Security and Access

- Only authorized Practitioners can record flags.
- All POST actions are logged and audited.