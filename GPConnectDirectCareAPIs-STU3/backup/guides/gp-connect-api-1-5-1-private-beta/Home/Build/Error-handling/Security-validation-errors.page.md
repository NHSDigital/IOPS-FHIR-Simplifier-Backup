## {{page-title}}

When responding to consumer API requests, provider systems **SHALL** return one of the following `OperationOutcome` details when enforcement of local consent rules result in an error condition:

|HTTP code|Issue type|Spine error code - code|Spine error code - display|
|---|---|---|---|
|`403`|forbidden|NO_PATIENT_CONSENT|Patient has not provided consent to share data|
|`403`|forbidden|NO_ORGANISATION_CONSENT|Organisation has not provided consent to share data|
|`403`|forbidden|ACCESS DENIED|Access denied|
|`403`|forbidden|NO_RELATIONSHIP|No legitimate relationship exists with this patient|

### Example: No patient consent to share

For example, if the patient has requested that their record should not be shared then the following error details would be returned:

```json
{
  "resourceType": "OperationOutcome",
  "meta": {
    "profile": [
      "https://fhir.nhs.uk/STU3/StructureDefinition/GPConnect-OperationOutcome-1"
    ]
  },
  "issue": [
    {
      "severity": "error",
      "code": "forbidden",
      "details": {
        "coding": [
          {
            "system": "https://fhir.nhs.uk/STU3/ValueSet/Spine-ErrorOrWarningCode-1",
            "code": "NO_PATIENT_CONSENT",
            "display": "Patient has not provided consent to share data"
          }
        ]
      }
    }
  ]
}
```

### Example: Access denied

```json
{
  "resourceType": "OperationOutcome",
  "meta": {
    "profile": [
      "https://fhir.nhs.uk/STU3/StructureDefinition/GPConnect-OperationOutcome-1"
    ]
  },
  "issue": [
    {
      "severity": "error",
      "code": "forbidden",
      "details": {
        "coding": [
          {
            "system": "https://fhir.nhs.uk/STU3/ValueSet/Spine-ErrorOrWarningCode-1",
            "code": "ACCESS_DENIED",
            "display": "Access denied"
          }
        ]
      },
      "diagnostics": "The Access Document capability is disabled at this practice."
    }
  ]
}
```

---