## {{page-title}}

When responding to consumer API requests, provider systems **SHALL** return one of the following `OperationOutcome` details when a resource could not be created or updated because it would cause a duplicate in the provider system:

|HTTP code|Issue type|Spine error code - code|Spine error code - display|
|---|---|---|---|
|`409`|duplicate|DUPLICATE_REJECTED|Create would lead to creation of a duplicate resource|

### Example: Attempting to register a patient that already exists

For example, if the consumer attempted to register a patient that already has an active record on the provider system the error details would be returned:

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
      "code": "duplicate",
      "details": {
        "coding": [
          {
            "system": "https://fhir.nhs.uk/STU3/ValueSet/Spine-ErrorOrWarningCode-1",
            "code": "DUPLICATE_REJECTED",
            "display": "Create would lead to creation of duplicate resource"
          }
        ]
      },
      "diagnostics": "Patient record already exists with that NHS number"
    }
  ]
}
```

---