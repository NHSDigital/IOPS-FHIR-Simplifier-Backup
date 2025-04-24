# Retrieve PatientFlags

:::info
This page describes how a Practitioner retrieves Patient Flag records for a given patient using their NHSNumber via the `PatientFlag` FHIR API.
:::

## 📘 Overview

Patient Flags are clinical markers that provide important information about a patient. They can include alerts such as allergies, safeguarding issues, or specific care instructions.

For system-level context, see [Home](Home).

---

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

---

## 📋 User Story

> **As a Practitioner**, I want to retrieve PatientFlag records using a patient's NHSNumber, so that I can be alerted to any critical clinical information when making care decisions.

---

## 👥 Actors

| Actor                        | Description                                                |
|-----------------------------|------------------------------------------------------------|
| **Practitioner**            | Clinician accessing the system                             |
| **PatientFlag FHIR API**    | API endpoint exposing `PatientFlag` resources              |
| **FHIR Repository**         | Backend data store containing flag records                 |

---

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

---

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

---

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


---

## 🔍 Querying the API

Use the FHIR Search API to retrieve `PatientFlag` resources.

### Example Query

```http
GET [baseUrl]/PatientFlag?patient=9449306753
```

This retrieves all `PatientFlag` resources for the patient with NHSNumber `9449306753`.

> ℹ️ Uses [`Flag.patient`](http://www.hl7.org/fhir/R4/flag.html#search) search parameter.

---

## ✅ Response Examples

### 🟢 Successful Response

```json
{
  "resourceType": "Bundle",
  "type": "searchset",
  "total": 1,
  "entry": [
    {
      "resource": {
        "resourceType": "Flag",
        "id": "flag1",
        "status": "active",
        "code": {
          "text": "Allergy: Penicillin"
        },
        "subject": {
          "reference": "Patient/12345"
        }
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
