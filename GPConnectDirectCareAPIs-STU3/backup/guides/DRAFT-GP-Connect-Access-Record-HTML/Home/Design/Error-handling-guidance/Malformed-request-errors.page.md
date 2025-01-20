## {{page-title}}

When the server cannot or will not process a request due to an apparent client error (for example, malformed request syntax, too large size, and so on) then the following `BAD_REQUEST` error **MUST** be used to return debug details.

|HTTP Code|Error Code|Description|
|---|---|---|
|`400`|BAD_REQUEST|Submitted request is malformed / invalid.|

#### Example - Malformed request syntax

For example, if the request could not be understood by the server due to malformed syntax, then the following error details would be returned:

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
            "code": "BAD_REQUEST"
          }
        ]
      },
      "diagnostics": "Any further internal debug details i.e. stack trace details etc."
    }
  ]
}
```