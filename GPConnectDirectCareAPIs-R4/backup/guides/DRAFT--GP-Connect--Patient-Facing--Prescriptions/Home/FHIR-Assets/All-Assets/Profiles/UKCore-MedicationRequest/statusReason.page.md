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
        <td>Code</td>
        <td>Optional</td>
        <td>0..1</td>
      </tr>
    </tbody>
</table>

Where a medication/medical device has been stopped (status == ‘stopped’), the reason is provided in the statusReason extension.

Mandatory for authorisations with stopped status.

Only populate for a MedicationRequest with an intent = plan. Do not populate for a MedicationRequest with an intent = order.

### Example
```json
"statusReason": {
    "coding": [
        {
            "system": "https://fhir.nhs.uk/CodeSystem/medicationrequest-status-reason",
            "code": "0001",
            "display": "Prescribing Error"
        }
    ]
},
```

---