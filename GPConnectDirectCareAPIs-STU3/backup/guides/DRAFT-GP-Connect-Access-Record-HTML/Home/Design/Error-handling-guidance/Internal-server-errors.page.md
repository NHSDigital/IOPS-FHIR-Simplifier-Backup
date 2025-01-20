## {{page-title}}

When the error is **unexpected** and the server can’t be more specific on the exact nature of the problem then the following `INTERNAL_SERVER_ERROR` **MUST** be used to return debug details.

|HTTP Code|Error Code|Description|
|---|---|---|
|`500`|INTERNAL_SERVER_ERROR|Unexpected internal server error.|

When the FHIR server has received a request for an operation or FHIR resource which is not (yet) implemented, then the NOT_IMPLEMENTED **SHOULD** be used.

|HTTP Code|Error Code|Description|
|---|---|---|
|`501`|NOT_IMPLEMENTED|FHIR resource or operation not implemented at server|

#### Example - Unexpected exception

For example, an unexpected internal exception is thrown by either an Operation or RESTful API, then the following error details would be returned:

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
      "code": "exception",
      "details": {
        "coding": [
          {
            "system": "http://fhir.nhs.net/ValueSet/gpconnect-error-or-warning-code-1",
            "code": "INTERNAL_SERVER_ERROR"
          }
        ]
      },
      "diagnostics": "Any further internal debug details i.e. stack trace details etc."
    }
  ]
}
```
