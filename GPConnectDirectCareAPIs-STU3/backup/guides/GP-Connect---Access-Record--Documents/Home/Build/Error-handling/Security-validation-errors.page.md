## {{page-title}}

When responding to consumer API requests, provider systems **SHALL** return one of the following `OperationOutcome` details when enforcement of local consent rules result in an error condition:

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
      <td><code>403</code></td>
      <td>forbidden</td>
      <td>NO_PATIENT_CONSENT</td>
      <td>Patient has not provided consent to share data</td>
    </tr>
    <tr>
      <td><code>403</code></td>
      <td>forbidden</td>
      <td>NO_ORGANISATION_CONSENT</td>
      <td>Organisation has not provided consent to share data</td>
    </tr>
    <tr>
      <td><code>403</code></td>
      <td>forbidden</td>
      <td>ACCESS_DENIED</td>
      <td>Access denied</td>
    </tr>
  </tbody>
</table>

### Example: No patient consent to share
For example, if the patient has requested that their record should not be shared then the following error details would be returned:

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
      "code": "forbidden",
      "details": {
        "coding": [
          {
            "system": "https://fhir.nhs.uk/STU3/ValueSet/Spine-ErrorOrWarningCode-1",
            "code": "NO_PATIENT_CONSENT",
            "display": "Patient has not provided consent to share data"
          }
        ]
      }
    }
  ]
}
```


### Example: Access denied

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
      "code": "forbidden",
      "details": {
        "coding": [
          {
            "system": "https://fhir.nhs.uk/STU3/ValueSet/Spine-ErrorOrWarningCode-1",
            "code": "ACCESS_DENIED",
            "display": "Access denied"
          }
        ]
      },
      "diagnostics": "The Access Document capability is disabled at this practice."
    }
  ]
}
```

---