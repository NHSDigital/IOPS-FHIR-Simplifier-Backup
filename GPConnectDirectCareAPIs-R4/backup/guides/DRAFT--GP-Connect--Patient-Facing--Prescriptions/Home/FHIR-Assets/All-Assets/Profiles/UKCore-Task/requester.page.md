## {{page-title}}

<table data-responsive class="nhsd-!t-margin-bottom-6">
    <thead>
        <tr>
            <th>DataType</th>
            <th>Optionality</th>
            <th>Cardinality</th>
        </tr>
    </thead>
    <tbody>
      <tr>
        <td data-no-sort>Reference(Patient)</td>
        <td data-no-sort>Required</td>
        <td data-no-sort>0..1</td>
      </tr>
    </tbody>
</table>

In this use case, since it is Patient Facing the requester must always be the Patient. Beyond MVP this could be updated to facilitate proxy ordering.

### Example
```json
"requester" : {
    "reference" : "Patient/9000000009",
    "identifier" : {
      "system" : "https://fhir.nhs.uk/Id/nhs-number",
      "value" : 9000000009
    },
    "display" : "Jane Smith"
},
```

---