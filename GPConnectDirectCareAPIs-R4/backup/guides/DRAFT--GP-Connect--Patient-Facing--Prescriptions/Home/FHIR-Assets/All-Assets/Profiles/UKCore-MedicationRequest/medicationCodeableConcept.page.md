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
        <td>Mandatory</td>
        <td>1..1</td>
      </tr>
    </tbody>
</table>

* The medicationCodeableConcept.text should be the description for the medication.

* The medicationCodeableConcept.coding.code should be the code for the medication.
    * Supported codesystems: [DM+D](https://services.nhsbsa.nhs.uk/dmd-browser/)

* The medicationCodeableConcept.coding.display should be the description for the medication, i.e. the same value as medicationCodeableConcept.text.

### Example
```json
    "medicationCodeableConcept": [
      {
        "coding": [
          {
            "system": "https://dmd.nhs.uk",
            "code": 329526003,
            "display": "Apirin 300mg dispersible tablets"
          }
        ]
      }
    ],

```

---