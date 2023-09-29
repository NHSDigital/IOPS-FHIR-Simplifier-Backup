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
        <td>0..*</td>
      </tr>
    </tbody>
</table>

This **MUST** be populated with a globally unique and persistent identifier (that is, it doesn’t change between requests and therefore stored with the source data). This **MUST** be scoped by a provider specific namespace for the identifier.

Where consuming systems are integrating data from this resource to their local system, they **MUST** also persist this identifier at the same time.

If the EPS identifier is present (will only be with an `intent` of order) then the identifier.value is where the EPS Id SHOULD also be added. The codeSystem for this identifier is `https://fhir.nhs.uk/Id/prescription-order-item-number`

### Example of intent order with EPS Id
```json
    "identifier" : [
        {
            "system" : "https://fhir.nhs.uk/Id/prescription-order-item-number",
            "value" : "4857b9d3-b714-44b9-9e67-3df67275b785"
        },
    ]
```

### Example of intent plan with uuid
```json
"identifier": [
    {
        "system": "https://tools.ietf.org/html/rfc4122",
        "value": "42b4a841-9d69-4d13-bf91-ee5882e85765"
    }
],
```
### Comment
This is a business identifier, not a resource identifier.
---
