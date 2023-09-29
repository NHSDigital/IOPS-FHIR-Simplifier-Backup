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
        <td>Conditional</td>
        <td>0..*</td>
      </tr>
    </tbody>
</table>

This field is used to create the links between `MedicationRequest` profiles to represent the medication ordering process as described here. This MUST be used when a profile has an `intent` element that is set to `order` and is `basedOn` a `MedicationRequest` profile that has an `intent` set to `plan`.

DO NOT USE for authorisations - that is, for a `MedicationRequest` with `intent` of `plan`.

### Example

```json
"basedOn": [
    {
    "reference": "MedicationRequest/06c7d0e2-1022-4e47-ac55-f6463d701a4f"
    }
],
```

---