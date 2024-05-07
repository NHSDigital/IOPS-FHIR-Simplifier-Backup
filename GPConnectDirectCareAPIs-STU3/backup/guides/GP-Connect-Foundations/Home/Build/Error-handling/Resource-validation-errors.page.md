## {{page-title}}

Where FHIR resource validation issues arise during processing of consumer requests, provider systems **SHALL** utilise one the following error details:

|HTTP code|Issue type|Spine error code - code|Spine error code - display|
|---|---|---|---|
|`422`|invalid|INVALID_RESOURCE|Invalid validation of resource|
|`422`|invalid|INVALID_PARAMETER|Invalid parameter|
|`422`|invalid|REFERENCE_NOT_FOUND|Reference not found|

Detailed diagnostic information **MUST** be supplied when erroring on the codes above.

INVALID_PARAMETER would be used in the following, or similar, scenarios:

- Unexpected parameter value for a custom operation. For example, a lowercase value is supplied to the recordSection parameter of the $gpc.getcarerecord operation.

- An invalid date/time value specified in a custom operation parameter. For example, an invalid timePeriod defined in the timePeriod input parameter to the $gpc.getcarerecord operation.


INVALID_RESOURCE would be used in situations such as the following:

- Resource fails to validate against StructureDefinition (either in request body or in JSON Web Tokens (JWT) claim).

- A resource fails to be processed because of a FHIR constraint, or other rule application, where the error is not already covered by other error codes


REFERENCE_NOT_FOUND describes a scenario where a consumer POSTs a FHIR resource which contains a FHIR reference that cannot be found.

### Example: Reference not found
For example, when using the ‘Book an appointment’ API use case, a consumer includes a reference to a slot which does not exist at the server. The following error details would be returned:

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
      "code": "invalid",
      "details": {
        "coding": [
          {
            "system": "https://fhir.nhs.uk/STU3/ValueSet/Spine-ErrorOrWarningCode-1",
            "code": "REFERENCE_NOT_FOUND",
            "display": "FHIR reference not found"
          }
        ]
      },
      "diagnostics": "Reference to Slot/6 - no such slot exists at the server"
    }
  ]
}
```

---