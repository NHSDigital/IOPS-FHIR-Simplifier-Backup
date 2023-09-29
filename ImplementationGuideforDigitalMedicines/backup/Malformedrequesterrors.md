## {{page-title}}

When the server cannot or will not process a request due to an apparent client error then the following `BAD_REQUEST` error **MUST** be used to return debug details.

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
            <td><code>400</code></td>
            <td>invalid</td>
            <td><code>BAD_REQUEST</code></td>
            <td>Submitted request is malformed / invalid.</td>
        </tr>
    </tbody>
</table>

`BAD_REQUEST` [Spine](https://digital.nhs.uk/services/spine) error codes be used in the following types of scenario:

- JWT claims information is not valid JSON, is null, or has an invalid value
- invalid FHIR resource in JWT claim (for example, a `Patient` resource when `Practitioner` expected)
- malformed JSON or XML content in request body
- an expected header is missing or invalid
- invalid HTTP verb used

### Example: Malformed JSON Web Token in request

For example, if the request contained a null claim within a [JSON Web Token (JWT)](https://jwt.io/), then the following error details would be returned:

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
                        "code": "BAD_REQUEST",
                        "display": "Bad request"
                    }
                ]
            },
            "diagnostics": "Malformed JWT"
        }
    ]
}
```

---