# Remove PatientFlags

:::info
This page describes how a Practitioner removes Patient Flag records for a given patient using their NHSNumber via the PatientFlag FHIR API.
:::

## 📘 Overview

Patient Flags may need to be removed when they are incorrect, outdated, or no longer clinically appropriate. This operation removes the PatientFlag resource and all associated data.

For system-level context, see [Home](Home).

## 🩺 Use Case

A Practitioner removes a patient's flag records by calling the PatientFlag endpoint using the patient's NHSNumber and relevant search parameters.

### Use Case Diagram

<plantuml>
@startuml

skinparam actorStyle awesome
left to right direction

rectangle "Patient Flag"{
actor Practitioner as pra
usecase "Record" as record <<abstract>>
usecase "Remove Patient Flag record" as rem <<abstract>>
}


actor Patient as pat

usecase "Consult" as consult <<abstract>>

pat -- consult
pra -- consult
pra -- record
record <.. rem : include

@enduml
</plantuml>

## 📋 User Story

> **As a Practitioner**, I want to remove PatientFlag records using a patient’s NHSNumber and reason for removal, so that the patient’s record reflects only relevant and current information.

## 👥 Actors

| Actor                     | Description                                               |
|--------------------------|-----------------------------------------------------------|
| **Practitioner**         | Clinician removing the record                             |
| **PatientFlag FHIR API** | API endpoint exposing PatientFlag resources               |
| **FHIR Repository**      | Backend data store containing flag records                |

## ⚙️ Workflow

### Frequency of Use
- Occasionally

### Trigger
- Practitioner identifies a flag is no longer needed or was added in error

### Pre-conditions
- Practitioner has appropriate access
- Patient NHSNumber and reason for removal are known

### Post-conditions
- The PatientFlag and related resources are deleted, or an error is returned

## 🔄 Flow

### Main Flow

1. Practitioner sends a DELETE request to the PatientFlag API using NHSNumber and reason.
2. API locates the relevant PatientFlag resource(s).
3. Associated resources are also removed.
4. API returns an OperationOutcome confirming the deletion.

### Alternate Flow

| Step | Condition                             | Outcome                                              |
|------|---------------------------------------|------------------------------------------------------|
| 2a   | No matching resources                 | Return OperationOutcome with total: 0 or not-found   |
| 3a   | Failure deleting associated resources | API performs rollback and returns error              |

## 🧩 System Interaction

<plantuml>
@startuml

skinparam actorStyle hollow

actor        "Patient"          as pat
actor        "Practitioner"     as pra
participant  "FHIR API"         as api
entity       "Patient Flag"     as pfg
entity       "Additional Detail"  as add

  pat ->  pra : Remove
  pra ->  api : Remove
  api ->  pfg : Remove resource
  

loop for each Additional Detail resource
  api ->  add : Remove resource (any)
  add ->  add : Validate
  api <-- add : return
  alt Validation failed
    api -> api : rollback
  end
end

pra <-- api : OperationOutcome

@enduml
</plantuml>

## 🔍 Removing Flags via API

Use the FHIR [conditional delete](http://hl7.org/fhir/r4/http.html#3.1.0.7.1) method.

### 🧼 Remove All PatientFlags for a Patient

```
DELETE [baseURL]/PatientFlag?patient=9449306753&reason=NoLongerApplicable
```

- Deletes all PatientFlag resources for a patient
- Removes all associated supporting resources
- Requires both `patient` and `reason` query parameters

### 🧼 Remove Specific Flag Code for a Patient

```
DELETE [baseURL]/PatientFlag?patient=9449306753&code=NRAF&reason=Incorrect
```

- Deletes only the specified PatientFlag and its related resources
- Requires `patient`, `code`, and `reason` query parameters
- ℹ️ Deletion is based on standard FHIR query syntax and conditional operations.

### ✅ Response Examples

#### 🟢 Successful Deletion

```json
{
  "resourceType": "OperationOutcome",
  "issue": [
    {
      "severity": "information",
      "code": "informational",
      "diagnostics": "Deleted 1 PatientFlag and 2 associated resources"
    }
  ]
}
```

#### ⚪ No Matching Resources Found

```json
{
  "resourceType": "OperationOutcome",
  "issue": [
    {
      "severity": "warning",
      "code": "not-found",
      "diagnostics": "No PatientFlag found for patient 9449306753"
    }
  ]
}
```

#### 🔴 Error: Validation Failed on Deletion

```json
{
  "resourceType": "OperationOutcome",
  "issue": [
    {
      "severity": "error",
      "code": "processing",
      "diagnostics": "Unable to delete associated Condition resource due to constraint"
    }
  ]
}
```

## 🔐 Security and Access

- Only authorized Practitioners can perform deletions.

- All deletions are logged and audited.

---