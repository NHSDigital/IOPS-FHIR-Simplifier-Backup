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
        <td>Reference(Patient)</td>
        <td>required</td>
        <td>1..1</td>
      </tr>
    </tbody>
</table>


Who the medication/medical device is for - that is, to whom it will be administered.

Reference to Patient.

### Example
``` json
"subject": {
    "reference": "Patient/9000000009",
    "identifier": {
        "system": "https://fhir.nhs.uk/Id/nhs-number",
        "value": "9000000009"
    },
    "display": "Jane Smith"
},
```

---