## {{page-title}}

When the server cannot or will not process a request due to an apparent client error then the following `BAD_REQUEST` error SHALL be used to return debug details.

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
      <td><code class="highlighter-rouge">400</code></td>
      <td>invalid</td>
      <td>BAD_REQUEST</td>
      <td>Submitted request is malformed/invalid.</td>
    </tr>
  </tbody>
</table>

BAD_REQUEST Spine error codes should be used in the following types of scenario:

- JWT claims information is not valid JSON, is null, or has an invalid value

- invalid FHIR resource in JWT claim (for example, patient resource when practitioner expected)

- malformed JSON or XML content in request body

- an expected header (for example, interaction ID header) is missing or invalid

- invalid HTTP verb used (for example, using POST to read a patient)

- `InteractionID` header does not match request


### Example: Malformed JSON claim in request
For example, if the request contained a null aud claim in the JWT, then the following error details would be returned:

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
      "code": "invalid",
      "details": {
        "coding": [
          {
            "system": "https://fhir.nhs.uk/STU3/ValueSet/Spine-ErrorOrWarningCode-1",
            "code": "BAD_REQUEST",
            "display": "Bad request"
          }
        ]
      },
      "diagnostics": "Empty JWT aud claim"
    }
  ]
}
```

---