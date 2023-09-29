## {{page-title}}

When responding to consumer API requests, provider systems **MUST** return one of the following `OperationOutcome` details when a resource could not be created or updated because it would cause a duplicate in the provider system:

<table data-responsive>
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
            <td><code>409</code></td>
            <td>duplicate</td>
            <td><code>DUPLICATE_REJECTED</code></td>
            <td>Create would lead to creation of a duplicate resource</td>
        </tr>
    </tbody>
</table>

For example, if the ePMA system attempted to send a `MedicationRequest` that is already an active record on the pharmacy system the error details would be returned:

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
            "code": "duplicate",
            "details": {
                "coding": [
                {
                    "system": "https://simplifier.net/guide/NHSDigital/NHSDigital-OperationOutcome-Codes",
                    "code": "DUPLICATE_REJECTED",
                    "display": "Create would lead to creation of duplicate resource"
                }
            ]
        },
        "diagnostics": "MedicationRequest record already exists with that logical identifier"
    }
  ]
}
```