## {{page-title}}

<table data-responsive class="nhsd-!t-margin-bottom-6">
    <thead>
        <tr>
            <th data-no-sort>DataType</th>
            <th data-no-sort>Optionality</th>
            <th data-no-sort>Cardinality</th>
        </tr>
    </thead>
    <tbody>
      <tr>
      <td>Extension</td>
      <td>Conditional</td>
      <td>0..1</td>
      </tr>
    </tbody>
</table>

Extension elements to hold details of repeat authorisation.

Only populate for a `MedicationRequest` with an intent = plan. For a `MedicationRequest` with an intent = order none of the repeatInformation fields are populated.

This extension must be present for `continuous` therapy types.

### medicationRepeatInformation.authorisationExpiryDate
Only populate for a `MedicationRequest` with an intent = plan. For a `MedicationRequest` with an intent = order this is not populated.

### medicationRepeatInformation.numberOfPrescriptionsIssued
Running total of number of issues made against a repeat authorisation.

**MUST** be zero, if not yet issued.

### Example
```json
"extension": [
    {
        "url": "https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-MedicationRepeatInformation",
        "extension": [
            {
                "url": "numberOfPrescriptionsIssued",
                "valueUnsignedInt": 2
            },
            {
                "url": "authorisationExpiryDate",
                "valueDateTime": "2022-10-11T19:00:00.000Z"
            }
        ]
    }
],
```

---