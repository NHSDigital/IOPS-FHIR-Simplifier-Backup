## {{page-title}}

Provider systems **MUST** returning one of the following `OperationOutcome` error codes in the case of enforcing their local patient consent rules when responding to consumer API requests.

|HTTP Code|Error Code|Description|
|---|---|---|
|`403`|NO_PATIENT_CONSENT|No Patient Consent To Share|
|`403`|NON_AUTHORITATIVE|Non Authoritative|

#### Example - No patient consent to share

For example, the patient has requested that their record not be shared via the `$gpc.getcarerecord` Operation then the following error details would be returned:

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
      "code": "forbidden",
      "details": {
        "coding": [
          {
            "system": "http://fhir.nhs.net/ValueSet/gpconnect-error-or-warning-code-1",
            "code": "NO_PATIENT_CONSENT"
          }
        ]
      },
      "diagnostics": "Any further internal debug details i.e. stack trace details etc."
    }
  ]
}
```
