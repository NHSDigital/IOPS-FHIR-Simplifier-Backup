# Remove Patient Flag Associated Resources

This page describes how a Practitioner removes associated resources (e.g., additional details, conditions) from a Patient Flag record via the PatientFlag FHIR API.

## 📘 Overview

Patient Flags are used to track important clinical information about patients, such as allergies, conditions, or adjustments. In some cases, associated resources like conditions or adjustments may need to be removed or updated. This process ensures that the information related to the flag is properly maintained.

For system-level context, see [Home](Home).

## 🩺 Use Case

A Practitioner removes associated resources from a Patient Flag record. This includes resources such as conditions or adjustments linked to the flag, and can be done via the FHIR API.

### Use Case Diagram

<plantuml>
@startuml

skinparam actorStyle awesome
left to right direction

rectangle "Patient Flag"{
actor Practitioner as pra
usecase "Record" as record <<abstract>>
usecase "Add Additional Detail" as add <<abstract>>
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

> As a Practitioner, I want to remove associated resources from a Patient Flag, so that I can ensure that the patient's record accurately reflects their current status, removing unnecessary or outdated information.

## 👥 Actors

| Actor                     | Description                                                    |
|--------------------------|----------------------------------------------------------------|
| **Practitioner**         | Clinician accessing the system to manage patient flags and associated resources. |
| **PatientFlag FHIR API** | API endpoint exposing PatientFlag and associated resource endpoints. |
| **FHIR Repository**      | Backend data store containing flag records and their associated resources. |

## ⚙️ Workflow

### Frequency of Use
- As needed when a practitioner needs to remove associated resources from a Patient Flag record.

### Trigger
- Practitioner decides to remove an associated resource for a patient.

### Pre-conditions
- Practitioner has identified the Patient Flag and associated resources.
- Practitioner is authorized to delete these resources.

### Post-conditions
- Associated resources are successfully deleted.
- The Patient Flag record is updated accordingly.

## 🔄 Flow

### Main Flow

1. Practitioner sends a request to remove the associated resource via the PatientFlag FHIR API.
2. The API queries the relevant PatientFlag and associated resources.
3. The API deletes the specified associated resource(s).
4. The Practitioner receives an OperationOutcome message confirming the successful deletion of the associated resources.

### Alternate Flow

| Step | Condition                      | Outcome                                               |
|------|--------------------------------|-------------------------------------------------------|
| 3a   | Associated resource not found  | Return an OperationOutcome indicating resource not found. |

## 🧩 System Interaction

<plantuml>
@startuml

skinparam actorStyle hollow

actor        "Patient"          as pat
actor        "Practitioner"     as pra
boundary     "FHIR API"         as api
entity       "Additional Detail"  as add

pra ->  pat : Consult patient
pra ->  api : Record adjustment record (transaction Bundle)

api ->  add : Create/update resource
add ->  add : Validate
api <-- add : return
alt Validation failed
  api -> api : rollback
end

pra <-- api : OperationOutcome

@enduml
</plantuml>

## 🔍 Querying the API

Use the FHIR Delete API to remove the Patient Flag and its associated resources.

### Example Query

To delete an associated resource (e.g., a Condition resource):

```
DELETE [baseURL]/Condition/[condition-id]?reason=[reason]
```

For example:

```
DELETE [baseURL]/Condition/b8ab463d-f698-41a0-aae2-6d6163dd0825?reason=Outdated
```

This removes the Condition resource with the specified ID and includes a reason for the deletion.

### ⚪ No Associated Resources Found

```json
{
  "resourceType": "OperationOutcome",
  "issue": [
    {
      "severity": "information",
      "code": "not-found",
      "diagnostics": "No associated resources found for PatientFlag with id [PatientFlag-id]."
    }
  ]
}
```

## 🔐 Security and Access

- Access to delete resources requires proper authentication and authorization.

- All delete operations are logged for auditing purposes.

---