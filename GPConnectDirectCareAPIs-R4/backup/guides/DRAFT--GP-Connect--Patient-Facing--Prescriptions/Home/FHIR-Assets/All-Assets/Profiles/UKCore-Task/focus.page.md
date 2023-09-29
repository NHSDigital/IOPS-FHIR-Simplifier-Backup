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
        <td>Reference(MedicationRequest)</td>
        <td>Required</td>
        <td>0..1</td>
      </tr>
    </tbody>
</table>

The focus must point to a previous {{pagelink:Home/FHIR-Assets/All-Assets/Profiles/UKCore-MedicationRequest/Index.page.md}} when requesting an instance of a prescription. The `MedicationRequest` must have an intent of `plan`. 

In returning the Task resource the provider must return a short summary of the referenced medication resource under the `display` element with the corresponding reference.

This display must contain the type of prescription, i.e. repeat, acute etc. and the title of the medication. See the example below.

### Example
```json
  "focus": {
    "reference": "MedicationRequest/b269d1d7-1acf-47bb-8b3c-e38b583d9a07"
    "display": "Repeat prescription for Pulmicort 100 Turbohaler (AstraZeneca UK Ltd)"
  },
```

---