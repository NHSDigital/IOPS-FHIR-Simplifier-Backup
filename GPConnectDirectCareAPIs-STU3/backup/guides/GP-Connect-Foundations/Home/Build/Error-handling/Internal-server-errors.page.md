## {{page-title}}

When the FHIR server has received a request for an operation or FHIR resource which is not (yet) implemented, then the NOT_IMPLEMENTED Spine error code **SHALL** be used.

|HTTP code|Issue type|Spine error code - code|Spine error code - display|
|---|---|---|---|
|`501`|not-supported|NOT_IMPLEMENTED|Not implemented|

When the error is unexpected and the server can’t be more specific on the exact nature of the problem then the `INTERNAL_SERVER_ERROR` Spine error code SHALL be used, and diagnostics SHALL be included to provide detail of the error

|HTTP code|Issue type|Spine error code - code|Spine error code - display|
|---|---|---|---|
|`500`|processing|INTERNAL_SERVER_ERROR|Unexpected internal server error|

### Example: Unexpected exception
For example, if an unexpected internal exception is thrown by either an Operation or RESTful API, then the following error details would be returned:

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
      "code": "exception",
      "details": {
        "coding": [
          {
            "system": "https://fhir.nhs.uk/STU3/ValueSet/Spine-ErrorOrWarningCode-1",
            "code": "INTERNAL_SERVER_ERROR",
            "display": "Internal server error"
          }
        ]
      },
      "diagnostics": "Any further internal debug details i.e. stack trace details etc."
    }
  ]
}
```

---