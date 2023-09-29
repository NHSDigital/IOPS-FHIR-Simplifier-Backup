## {{page-title}}

Provider systems **MUST** respond by returning one of the following `OperationOutcome` error codes where FHIR resource identity error scenarios are encountered:

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
            <td>value</td>
            <td><code>INVALID_IDENTIFIER_SYSTEM</code></td>
            <td>Invalid identifier system</td>
        </tr>
        <tr>
            <td><code>400</code></td>
            <td>value</td>
            <td><code>INVALID_IDENTIFIER_VALUE</code></td>
            <td>Invalid identifier value</td>
        </tr>
        <tr>
            <td><code>400</code></td>
            <td>value</td>
            <td><code>INVALID_NHS_NUMBER</code></td>
            <td>NHS number invalid</td>
        </tr>
        <tr>
            <td><code>404</code></td>
            <td>not-found</td>
            <td><code>ORGANISATION_NOT_FOUND</code></td>
            <td>Organisation record not found</td>
        </tr>
        <tr>
            <td><code>404</code></td>
            <td>not-found</td>
            <td><code>PATIENT_NOT_FOUND</code></td>
            <td>Patient record not found</td>
        </tr>
        <tr>
            <td><code>404</code></td>
            <td>not-found</td>
            <td><code>PRACTITIONER_NOT_FOUND</code></td>
            <td>Practitioner record not found</td>
        </tr>
        <tr>
            <td><code>404</code></td>
            <td>not-found</td>
            <td><code>NO_RECORD_FOUND</code></td>
            <td>No record found</td>
        </tr>
    </tbody>
</table>

### Example: An invalid NHS Number was supplied

In this scenario an invalid NHS number value was supplied. 

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
            "code": "value",
            "details": {
                "coding": [
                    {
                        "system": "https://simplifier.net/guide/NHSDigital/NHSDigital-OperationOutcome-Codes",
                        "code": "INVALID_NHS_NUMBER",
                        "display": "Invalid NHS number"
                    }
                ]
            }
        }
    ]
}
```

### Example: The patient could not be found

In this scenario a valid NHS number value was supplied; however, a local record did not exist for the patient in question.

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

---