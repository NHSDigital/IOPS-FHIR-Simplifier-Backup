## {{page-title}}

Provider systems **MUST** respond by returning one of the following `OperationOutcome` error codes in the case of a custom operation error (for example,`$gpc.getcarerecord`, `$gpc.registerpatient`).

|HTTP Code|Error Code|Description|
|---|---|---|
|`400`|INVALID_IDENTIFIER_SYSTEM|Invalid identifier system|
|`400`|INVALID_IDENTIFIER_VALUE|Invalid identifier value|
|`400`|INVALID_PATIENT_DEMOGRAPHICS|Invalid patient demographics (i.e. PDS trace failed)|
|`404`|PATIENT_NOT_FOUND|Patient record not found|
|`400`|INVALID_NHS_NUMBER|NHS Number invalid|
|`404`|ORGANISATION_NOT_FOUND|Organisation record not found|
|`400`|INVALID_ODS_CODE|ODS code invalid|
|`404`|PRACTITIONER_NOT_FOUND|Practitioner record not found|

#### Example - Invalid NHS Number supplied

For example, if an invalid NHS Number value is supplied to the `$gpc.getcarerecord` Operation the following error details would be returned:

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
      "code": "value",
      "details": {
        "coding": [
          {
            "system": "http://fhir.nhs.net/ValueSet/gpconnect-error-or-warning-code-1",
            "code": "INVALID_NHS_NUMBER"
          }
        ]
      },
      "diagnostics": "Any further internal debug details i.e. stack trace details etc."
    }
  ]
}
```

#### Example - Patient not found

For example, a valid NHS Number value is supplied to the `$gpc.getcarerecord` Operation but no GP record exists for that patient then the following error details would be returned:

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
			"code": "not-found",
			"details": {
				"coding": [
					{
						"system": "http://fhir.nhs.net/ValueSet/gpconnect-error-or-warning-code-1",
						"code": "PATIENT_NOT_FOUND"
					}
				]
			},
			"diagnostics": "Any further internal debug details i.e. stack trace details etc."
		}
	]
}
```