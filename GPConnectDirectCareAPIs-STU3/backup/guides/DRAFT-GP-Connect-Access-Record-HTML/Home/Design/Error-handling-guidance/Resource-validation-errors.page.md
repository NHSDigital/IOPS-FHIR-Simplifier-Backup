## {{page-title}}

|HTTP Code|Error Code|Description|
|---|---|---|
|`422`|INVALID_RESOURCE|Submitted resource is not valid.|
|`422`|INVALID_PARAMETER|Submitted parameter is not valid.|
|`422`|REFERENCE_NOT_FOUND|Referenced resource not found.|

#### Example - Invalid reference

For example, if the RESTful API fails when an invalid organisational reference is supplied, then the following error details would be returned:

```json
{
  "resourceType": "OperationOutcome",
  "meta": {
    "profile": [
      "http://fhir.nhs.net/StructureDefinition/gpconnect-operationoutcome-1"
    ]
  },
  "issue": [
    {
      "severity": "error",
      "code": "invalid",
      "details": {
        "coding": [
          {
            "system": "http://fhir.nhs.net/ValueSet/gpconnect-error-or-warning-code-1",
            "code": "REFERENCE_NOT_FOUND"
          }
        ]
      },
      "diagnostics": "Any further internal debug details i.e. stack trace details etc."
    }
  ]
}
```
