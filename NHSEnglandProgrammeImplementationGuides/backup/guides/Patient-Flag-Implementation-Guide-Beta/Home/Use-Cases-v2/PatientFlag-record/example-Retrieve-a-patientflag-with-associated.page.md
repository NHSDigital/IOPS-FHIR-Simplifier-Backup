# Retrieve PatientFlag by Type and Details

:::info
This page explains how a Practitioner retrieves a specific type of PatientFlag (e.g., Reasonable Adjustment flag) along with all associated Additional Detail resources using both patient and code parameters.
:::

## 📘 Overview

This use case focuses on retrieving a PatientFlag record **of a specific type** using the `code` search parameter alongside the patient's NHSNumber.

For full context, see [Home](Home).

> 💡 Note: The standard FHIR `Flag` resource doesn't support searching by `code`. However, the `PatientFlag` used here is based on a custom profile with an extended search parameter: [England-Flag-Patient-Flag](Home/FHIR-Assets/Profiles/England-Flag-Patient-Flag.page.md) and its associated [England-FlagCode](Home/FHIR-Assets/SearchParameters/England-FlagCode.page.md).


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

```http
GET [baseUrl]/PatientFlag?patient=[NHSNumber]&code=[flagCode]
```

### Example:

```http
GET [baseUrl]/PatientFlag?patient=9449306753&code=NRAF
```

Returns the `PatientFlag` for patient `9449306753` of type `NRAF` (Reasonable Adjustment), plus any Additional Detail resources.

> 🔎 Uses custom search parameter defined in [England-FlagCode](Home/FHIR-Assets/SearchParameters/England-FlagCode.page.md).

---

## ✅ Response Examples

### 🟢 Successful Response

```json
{
  "resourceType": "Bundle",
  "type": "searchset",
  "entry": [
    {
      "resource": {
        "resourceType": "Flag",
        "code": {
          "coding": [{ "code": "NRAF", "display": "Reasonable Adjustment" }]
        }
      }
    },
    {
      "resource": {
        "resourceType": "QuestionnaireResponse",
        "status": "completed",
        "subject": { "reference": "Patient/12345" }
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
