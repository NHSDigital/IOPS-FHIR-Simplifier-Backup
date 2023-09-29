## {{page-title}}

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
      <td>value</td>
      <td>INVALID_IDENTIFIER_SYSTEM</td>
      <td>Invalid identifier system</td>
    </tr>
    <tr>
      <td><code class="highlighter-rouge">400</code></td>
      <td>value</td>
      <td>INVALID_IDENTIFIER_VALUE</td>
      <td>Invalid identifier value</td>
    </tr>
    <tr>
      <td><code class="highlighter-rouge">400</code></td>
      <td>value</td>
      <td>INVALID_NHS_NUMBER</td>
      <td>NHS number invalid</td>
    </tr>
    <tr>
      <td><code class="highlighter-rouge">400</code></td>
      <td>business-rule</td>
      <td>INVALID_PATIENT_DEMOGRAPHICS</td>
      <td>Invalid patient demographics (that is, PDS trace failed)</td>
    </tr>
    <tr>
      <td><code class="highlighter-rouge">404</code></td>
      <td>not-found</td>
      <td>ORGANISATION_NOT_FOUND</td>
      <td>Organisation record not found</td>
    </tr>
    <tr>
      <td><code class="highlighter-rouge">404</code></td>
      <td>not-found</td>
      <td>PATIENT_NOT_FOUND</td>
      <td>Patient record not found</td>
    </tr>
    <tr>
      <td><code class="highlighter-rouge">404</code></td>
      <td>not-found</td>
      <td>PRACTITIONER_NOT_FOUND</td>
      <td>Practitioner record not found</td>
    </tr>
    <tr>
      <td><code class="highlighter-rouge">404</code></td>
      <td>not-found</td>
      <td>NO_RECORD_FOUND</td>
      <td>No record found</td>
    </tr>
  </tbody>
</table>

### Example: Invalid NHS number supplied
If an invalid NHS number value is supplied to the `$gpc.getstructuredrecord` operation, the following error details would be returned:

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
      "code": "value",
      "details": {
        "coding": [
          {
            "system": "https://fhir.nhs.uk/STU3/ValueSet/Spine-ErrorOrWarningCode-1",
            "code": "INVALID_NHS_NUMBER",
            "display": "Invalid NHS number"
          }
        ]
      }
    }
  ]
}
```

### Example: Patient not found
For example, if a valid NHS number value is supplied to the `$gpc.getstructuredrecord` operation but no active GP record exists for that patient, then the following error details would be returned:

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
      "code": "not-found",
      "details": {
        "coding": [
          {
            "system": "https://fhir.nhs.uk/STU3/ValueSet/Spine-ErrorOrWarningCode-1",
            "code": "PATIENT_NOT_FOUND",
            "display": "Patient not found"
          }
        ]
      }
    }
  ]
}
```

### Example: Resource not found
This is a catch-all where a request for a resource instance cannot be found at the FHIR server, where more specific Spine error codes (such as PATIENT_NOT_FOUND) cannot be used.

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
      "code": "not-found",
      "details": {
        "coding": [
          {
            "system": "https://fhir.nhs.uk/STU3/ValueSet/Spine-ErrorOrWarningCode-1",
            "code": "NO_RECORD_FOUND",
            "display": "No record found"
          }
        ]
      }
    }
  ]
}
```

---