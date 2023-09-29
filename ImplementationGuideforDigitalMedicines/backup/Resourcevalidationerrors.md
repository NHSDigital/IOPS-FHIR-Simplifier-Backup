## {{page-title}}

Where FHIR resource validation issues arise during processing of consumer requests, provider systems **MUST** utilise one the following error details:

<table data-responsive">
    <thead>
        <tr>
            <th>HTTP code</th>
            <th>Issue type</th>
            <th>Error code</th>
            <th>Error message</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><code>422</code></td>
            <td>invalid</td>
            <td><code>INVALID_RESOURCE</code></td>
            <td>Submitted resource is not valid.</td>
        </tr>
        <tr>
            <td><code>422</code></td>
            <td>invalid</td>
            <td><code>INVALID_PARAMETER</code></td>
            <td>Submitted parameter is not valid.</td>
        </tr>
        <tr>
            <td><code>422</code></td>
            <td>invalid</td>
            <td><code>REFERENCE_NOT_FOUND</code></td>
            <td>Referenced resource not found.</td>
        </tr>
    </tbody>
</table>

Detailed diagnostic information **MUST** be supplied when erroring on the codes above.

`INVALID_PARAMATER` would be used in the following, or similar, scenarios:

- An invalid date / time value specified in a custom operation parameter.


`INVALID_RESOURCE` would be used in situations such as the following:

- The resource failed structural validation
- A resource failed to be procesed because of a FHIR constraint, or other rule application, where the error is not already covered by other error codes


`REFERENCE_NOT_FOUND` describes a scenario where a consumer `POST`s a FHIR resource which contains a FHIR reference that cannot be found.

### Example: Reference not found

For example, if a `MedicationRequest` referenced a `Practitioner` resource that could not be found or resolved by the server. The following error details would be returned:

```json
{
    "resourceType": "OperationOutcome",
    "meta": {
        "profile": [
            "https://fhir.nhs.uk/StructureDefinition/NHSDigital-OperationOutcome"
        ]
    },
    "issue": [
        {
            "severity": "error",
            "code": "invalid",
            "details": {
                "coding": [
                    {
                        "system": "https://simplifier.net/guide/NHSDigital/NHSDigital-OperationOutcome-Codes",
                        "code": "REFERENCE_NOT_FOUND",
                        "display": "FHIR reference not found"
                    }
                ]
            },
            "diagnostics": "Referenced Practitioner resource not found"
        }
    ]
}
```

---