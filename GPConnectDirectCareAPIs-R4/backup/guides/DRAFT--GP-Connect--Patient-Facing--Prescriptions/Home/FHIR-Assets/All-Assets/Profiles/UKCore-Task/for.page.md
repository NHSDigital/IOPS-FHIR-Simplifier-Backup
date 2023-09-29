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
        <td>Required</td>
        <td>0..1</td>
      </tr>
    </tbody>
</table>

This must reference the patient that the request is for, using NHS number as the ID.

### Example
```json
  "for" : {
    "reference" : "Patient/9000000009",
    "identifier" : {
      "system" : "https://fhir.nhs.uk/Id/nhs-number",
      "value" : 9000000009
    },
    "display" : "Jane Smith"
  },
```

---