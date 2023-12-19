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
        <td>Required</td>
        <td>0..*</td>
      </tr>
    </tbody>
</table>

Must be set to "community" as this includes requests for medications to be administered or consumed by the patient in their home (this would include long term care or nursing homes, hospices, etc.) 

### Example
```json
    "category": [
      {
        "coding": [
          {
            "system": "http://fhir.hl7.org/CodeSystem/medicationrequest-category",
            "code": "community",
            "display": "Community"
          }
        ]
      }
    ],
```

---
