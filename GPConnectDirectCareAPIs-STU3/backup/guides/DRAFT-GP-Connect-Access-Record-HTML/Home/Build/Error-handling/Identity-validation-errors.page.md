## {{page-title}}

Provider systems **SHALL** respond by returning one of the following `OperationOutcome` error codes where FHIR resource identity error scenarios are encountered:

|HTTP code|Issue type|Spine error code - code|Spine error code - display|
|---|---|---|---|
|`400`|value|INVALID_IDENTIFIER_SYSTEM|Invalid identifier system|
|`400`|value|INVALID_IDENTIFIER_VALUE|Invalid identifier value|
|`400`|value|INVALID_NHS_NUMBER|Invalid NHS number|
|`400`|business-rule|INVALID_PATIENT_DEMOGRAPHICS|Invalid patient demographics (that is, PDS trace failed)|
|`404`|not-found|ORGANISATION_NOT_FOUND|Organisation not found|
|`404`|not-found|PATIENT_NOT_FOUND|Patient not found|
|`404`|not-found|PRACTITIONER_NOT_FOUND|Practitioner not found|
|`404`|not-found|NO_RECORD_FOUND|No record found|

### Example: Invalid NHS number supplied

If an invalid NHS number value is supplied to the `$gpc.getstructuredrecord` operation, the following error details would be returned:

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
      "code": "value",
      "details": {
        "coding": [
          {
            "system": "https://fhir.nhs.uk/STU3/ValueSet/Spine-ErrorOrWarningCode-1",
            "code": "INVALID_NHS_NUMBER",
            "display": "Invalid NHS number"
          }
        ]
      }
    }
  ]
}
```

### Example: Patient not found

For example, if a valid NHS number value is supplied to the `$gpc.getstructuredrecord` operation but no active GP record exists for that patient, then the following error details would be returned:

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
      "code": "not-found",
      "details": {
        "coding": [
          {
            "system": "https://fhir.nhs.uk/STU3/ValueSet/Spine-ErrorOrWarningCode-1",
            "code": "PATIENT_NOT_FOUND",
            "display": "Patient not found"
          }
        ]
      }
    }
  ]
}
```

### Example: Resource not found

This is a catch-all where a request for a resource instance cannot be found at the FHIR server, where more specific Spine error codes (such as PATIENT_NOT_FOUND) cannot be used.

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
      "code": "not-found",
      "details": {
        "coding": [
          {
            "system": "https://fhir.nhs.uk/STU3/ValueSet/Spine-ErrorOrWarningCode-1",
            "code": "NO_RECORD_FOUND",
            "display": "No record found"
          }
        ]
      }
    }
  ]
}
```

---