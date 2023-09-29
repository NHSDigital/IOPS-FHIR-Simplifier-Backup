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
          <td>Reference</td>
          <td>Required</td>
          <td>0..*</td>
      </tr>
    </tbody>
</table>

Must reference a `MedicationRequest` within the `basedOn` attribute: `MedicationRequests` provide details of specific prescriptions. The referenced `MedicationRequest` must have intent of `plan`.

The display within `basedOn` should quote the `courseOfTherapyType` from the referenced `MedicationRequest`, showing the prescription treatment type.

#### Example

```json
      "basedOn" : {
        "reference" : "MedicationRequest/0f450c33-67b2-4ca3-b0f9-fea75ccdcd44",
        "display" : "Prescription request for Amoxicillin 250mg capsules."
      },
```

---