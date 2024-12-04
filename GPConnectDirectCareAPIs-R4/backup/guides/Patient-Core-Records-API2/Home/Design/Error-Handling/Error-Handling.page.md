## {{page-title}}

All errors should be reported using a the [FHIR UK Core OperationOutcome](https://simplifier.net/hl7fhirukcorer4/ukcore-operationoutcome) international resource.

All responses would be immediate with any content-specific errors to be presented by the OperationOutcome resource.


Example

```json
{
  "resourceType": "OperationOutcome",
  "issue": [
    {
      "severity": "error",
      "code": "value",
      "details": {
        "coding": [
          {
            "system": "https://fhir.nhs.uk/CodeSystem/http-error-codes",
            "code": "NOT_FOUND",
            "display": "The requested resource was not found on the source system."
          }
        ]
      }
    }
  ]
}
```

Depending on the requirements, the code system would need to be updated with additional values.