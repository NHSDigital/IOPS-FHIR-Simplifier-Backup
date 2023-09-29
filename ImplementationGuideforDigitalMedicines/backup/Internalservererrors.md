## {{page-title}}

When the FHIR server has received a request for an operation or FHIR resource which is not (yet) implemented, then the `NOT_IMPLEMENTED` Spine error code MUST be used.

<table data-resonsive>
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
            <td><code>501</code></td>
            <td>not-supported</td>
            <td><code>NOT_IMPLEMENTED</code></td>
            <td>FHIR resource or operation not implemented at server.</td>
        </tr>
    </tbody>
</table>

When the error is unexpected and the server can’t be more specific on the exact nature of the problem then the `INTERNAL_SERVER_ERROR` Spine error code **MUST** be used, and diagnostics **MUST** be included to provide detail of the error.

<table class="table">
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
            <td><code>500</code></td>
            <td>processing</td>
            <td><code>INTERNAL_SERVER_ERROR</code></td>
            <td>Unexpected internal server error.</td>
        </tr>
    </tbody>
</table>

### Example: Unexpected exception

For example, if an unexpected internal exception is thrown by either an Operation or RESTful API, then the following error details would be returned:

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
            "code": "exception",
            "details": {
                "coding": [
                    {
                        "system": "https://simplifier.net/guide/NHSDigital/NHSDigital-OperationOutcome-Codes",
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