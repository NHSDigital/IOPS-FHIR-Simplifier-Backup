## {{page-title}}

When the FHIR server has received a request for an operation or FHIR resource which is not (yet) implemented, then the NOT_IMPLEMENTED Spine error code **SHALL** be used.

<table class="nhsd-!t-margin-bottom-6">
  <thead>
    <tr>
      <th data-no-sort>HTTP code</th>
      <th data-no-sort>Issue type</th>
      <th data-no-sort>Spine error code - code</th>
      <th data-no-sort>Spine error code - display</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code class="highlighter-rouge">501</code></td>
      <td>not-supported</td>
      <td>NOT_IMPLEMENTED</td>
      <td>FHIR resource or operation not implemented at server</td>
    </tr>
  </tbody>
</table>

When the error is unexpected and the server can’t be more specific on the exact nature of the problem then the `INTERNAL_SERVER_ERROR` Spine error code SHALL be used, and diagnostics SHALL be included to provide detail of the error

<table class="nhsd-!t-margin-bottom-6">
  <thead>
    <tr>
      <th data-no-sort>HTTP code</th>
      <th data-no-sort>Issue type</th>
      <th data-no-sort>Spine error code - code</th>
      <th data-no-sort>Spine error code - display</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code class="highlighter-rouge">500</code></td>
      <td>processing</td>
      <td>INTERNAL_SERVER_ERROR</td>
      <td>Unexpected internal server error.</td>
    </tr>
  </tbody>
</table>

### Example: Unexpected exception
For example, if an unexpected internal exception is thrown by either an Operation or RESTful API, then the following error details would be returned:

```xml
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