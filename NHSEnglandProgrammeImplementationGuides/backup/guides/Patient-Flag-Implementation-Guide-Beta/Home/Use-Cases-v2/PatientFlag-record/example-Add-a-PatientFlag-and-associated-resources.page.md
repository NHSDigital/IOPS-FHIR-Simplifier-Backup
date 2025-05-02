# Add PatientFlag with Associated Resources

:::info
This page describes how a Practitioner adds a PatientFlag record, along with associated FHIR resources, in a single transaction using the `PatientFlag` FHIR API.
:::

## 📘 Overview

Patient Flags may include associated clinical resources (e.g. Conditions, Observations) to provide a full picture of the patient's status.

For system-level context, see [Home](Home).

## 🩺 Use Case

A Practitioner adds a PatientFlag record and supporting FHIR resources in a single transaction bundle via the `PatientFlag` API.

### Use Case Diagram

<plantuml>
@startuml
skinparam actorStyle awesome
left to right direction

rectangle "Patient Flag" {
  actor Practitioner as pra
  usecase "Record" as record <<abstract>>
  usecase "Add Patient Flag record" as add <<abstract>>
}

pra -- record
record <.. add : include
@enduml
</plantuml>

## 📋 User Story

> **As a Practitioner**, I want to record a PatientFlag and related FHIR resources in a single transaction, so that I can maintain consistent and complete patient records.

## 👥 Actors

| Actor                        | Description                                                |
|-----------------------------|------------------------------------------------------------|
| **Practitioner**            | Clinician recording the patient flag                       |
| **PatientFlag FHIR API**    | API endpoint for submitting PatientFlag and related data   |
| **FHIR Repository**         | Backend storage that accepts transaction bundles           |

## ⚙️ Workflow

### Frequency of Use
- As needed

### Trigger
- Practitioner identifies the need to add or update a flag and related records.

### Pre-conditions
- Practitioner has appropriate access and identifiers (e.g. NHSNumber).
- No conflicting or duplicate flag types exist for the patient.

### Post-conditions
- PatientFlag and associated resources are stored as a unit.
- A confirmation or error message is returned.

## 🔄 Flow

### Main Flow

1. Practitioner constructs a transaction `Bundle` with:
   - `PatientFlag` resource
   - Supporting resources (e.g. `Condition`, `Observation`)
2. Practitioner submits the transaction bundle to the API.
3. API validates and stores all resources.
4. API returns a confirmation `OperationOutcome`.

### Alternate Flow

| Step | Condition                                   | Outcome                                              |
|------|---------------------------------------------|------------------------------------------------------|
| 3a   | Validation fails for any resource            | Entire bundle is rolled back; error returned         |
| 3b   | Duplicate flag of same type found            | Merge additional resources into existing flag        |

## 🧩 System Interaction

<plantuml>
@startuml

skinparam actorStyle hollow

actor        "Practitioner"     as pra
boundary     "FHIR API"         as api
entity       "Patient Flag"     as flg
entity       "Additional Detail"  as add

pra ->  api : Submit transaction Bundle

api ->  flg : Create/update PatientFlag
flg ->  flg : Validate
alt Validation failed
  api -> api : Rollback transaction
end

loop for each supporting resource
  api -> add : Create/update resource
  add -> add : Validate
  alt Validation failed
    api -> api : Rollback transaction
  end
end

pra <-- api : OperationOutcome

@enduml
</plantuml>

## 🔍 Submitting the Transaction

Use the FHIR `Bundle` [transaction](http://hl7.org/fhir/R4/bundle.html#transaction) interaction.

### Example Request

```
POST [baseUrl]/
```

```json
{
  "resourceType": "Bundle",
  "type": "transaction",
  "entry": [
    {
      "resource": {
        "resourceType": "Flag",
        "status": "active",
        "code": {
          "coding": [
            {
              "system": "https://fhir.nhs.uk/England/CodeSystem/England-FlagCategoryPatient",
              "code": "national-reasonable-adjustment-flag"
            }
          ]
        },
        "subject": {
          "reference": "Patient/1234567890"
        }
      },
      "request": {
        "method": "POST",
        "url": "Flag"
      }
    },
    {
      "resource": {
        "resourceType": "Condition",
        "clinicalStatus": {
          "coding": [
            {
              "system": "http://terminology.hl7.org/CodeSystem/condition-clinical",
              "code": "active"
            }
          ]
        },
        "subject": {
          "reference": "Patient/1234567890"
        }
      },
      "request": {
        "method": "POST",
        "url": "Condition"
      }
    }
  ]
}
```

## ✅ Response

### 🟢 Success

```json
{
  "resourceType": "Bundle",
  "type": "transaction-response",
  "entry": [
    { "response": { "status": "201 Created", "location": "Flag/1" } },
    { "response": { "status": "201 Created", "location": "Condition/1" } }
  ]
}
```

### 🔴 Failure (Validation)

```json
{
  "resourceType": "OperationOutcome",
  "issue": [
    {
      "severity": "error",
      "code": "invalid",
      "diagnostics": "Condition.subject is missing"
    }
  ]
}
```

---

## 🔐 Security and Access

- Authentication and authorization are required.
- Transactions are logged and auditable.

---
