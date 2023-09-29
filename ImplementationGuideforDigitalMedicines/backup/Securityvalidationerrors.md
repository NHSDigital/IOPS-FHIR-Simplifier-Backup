## {{page-title}}

When a client system does not present correct security parameters, provider systems **MUST** return one of the following `OperationOutcome` details:

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
            <td><code>403</code></td>
            <td>forbidden</td>
            <td><code>ACCESS_DENIED</code></td>
            <td>Access denied</td>
        </tr>
    </tbody>
</table>

### Example: Access denied

In this scenario as resource has attempted to be accessed which the requesting user is not authoriused to view.

The JSON below represents an example response that could be returned.

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
        "code": "forbidden",
        "details": {
            "coding": [
                {
                    "system": "https://simplifier.net/guide/NHSDigital/NHSDigital-OperationOutcome-Codes",
                    "code": "ACCESS_DENIED",
                    "display": "Access denied"
                }
            ]
        },
        "diagnostics": "Invalid authorisation token."
    }
  ]
}
```

---