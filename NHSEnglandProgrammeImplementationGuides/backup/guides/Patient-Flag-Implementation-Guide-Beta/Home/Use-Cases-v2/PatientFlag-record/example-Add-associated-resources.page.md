# Add Associated Resources

:::info
This page describes how a Practitioner records Additional Detail to support or enrich an existing PatientFlag using the relevant FHIR endpoints.
:::

## 📘 Overview

Practitioners may wish to associate additional detail—such as impairments, underlying conditions, or specific adjustments—to a PatientFlag to provide clearer clinical context or enrich decision-making.

For system-level context, see [Home](Home).

## 🩺 Use Case

A Practitioner records associated resources (e.g., Condition, Adjustment) related to a PatientFlag to provide supplementary clinical information.

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

> **As a Practitioner**, I want to add associated resources (Additional Detail) to a PatientFlag record so that care teams have access to more complete clinical context for a patient.

## 👥 Actors

| Actor                        | Description                                                    |
|-----------------------------|----------------------------------------------------------------|
| **Practitioner**            | Clinician recording the associated information                 |
| **Patient**                 | Individual whose data is being managed                         |
| **FHIR API**                | Endpoint receiving the resources                               |
| **Additional Detail**       | Any supporting FHIR resource (e.g. Condition, Adjustment)      |

## ⚙️ Workflow

### Frequency of Use
- As needed

### Trigger
- Practitioner decides to record supporting information.

### Pre-conditions
- Practitioner is authorized and has identified a relevant PatientFlag.

### Post-conditions
- Associated resource is stored and linked to the PatientFlag.

## 🔄 Flow

### Main Flow

1. Practitioner consults with the patient.
2. Practitioner prepares an associated resource (e.g., Condition).
3. Practitioner submits the resource via the FHIR API.
4. The system validates and stores the resource.
5. Practitioner receives a response (success or OperationOutcome).

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

Use [FHIR create](http://hl7.org/fhir/r4/http.html#create) to write an associated resource.

### Example

```
POST [baseURL]/[resourceType]
```

✅ Response Example

🟢 Successful OperationOutcome

```json
{
  "resourceType": "OperationOutcome",
  "issue": [
    {
      "severity": "information",
      "code": "informational",
      "diagnostics": "Resource created successfully."
    }
  ]
}
```
🔴 Error OperationOutcome

```json
{
  "resourceType": "OperationOutcome",
  "issue": [
    {
      "severity": "error",
      "code": "invalid",
      "diagnostics": "Missing or invalid required fields."
    }
  ]
}
```

🔐 Security and Access
- API requires authentication and authorization.

- All resource creation attempts are logged for auditing.