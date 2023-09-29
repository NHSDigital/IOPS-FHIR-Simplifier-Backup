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
        <td>Mandatory</td>
        <td>1..1</td>
      </tr>
    </tbody>
</table>

Reference to the patient that the medication is for.

### Example
```json
  "subject" : {
    "reference" : "Patient/9000000009",
    "identifier" : {
      "system" : "https://fhir.nhs.uk/Id/nhs-number",
      "value" : "9000000009"
    },
    "display" : "Jane Smith"
  },
```

---