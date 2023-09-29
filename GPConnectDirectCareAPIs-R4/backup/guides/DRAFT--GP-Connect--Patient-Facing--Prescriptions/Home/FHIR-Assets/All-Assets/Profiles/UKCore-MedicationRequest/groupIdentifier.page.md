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
        <td>Identifier</td>
        <td>Required</td>
        <td>0..1</td>
      </tr>
    </tbody>
</table>

The EPS prescriptionID if this medication or medical device has been prescribed via the Electronic Prescriptions Service. The element in the Identifier data type that MUST be populated when a groupIdentifier is populated is identifier.value.

All EPS prescribed drugs *MUST* have the prescriptionID present in this field and have system element set to https://fhir.nhs.uk/Id/prescription-order-number.

### Example

```json
 "groupIdentifier" : {
    "system" : "https://fhir.nhs.uk/Id/prescription-order-number",
    "value" : "PDI12E-Y765908-4FF3LQ"
  },
```

---