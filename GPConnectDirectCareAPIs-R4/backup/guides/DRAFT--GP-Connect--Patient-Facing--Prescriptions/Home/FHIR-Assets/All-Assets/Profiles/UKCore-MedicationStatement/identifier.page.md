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

This must be populated with a globally unique and persistent identifier (that is, it doesn’t change between requests and therefore stored with the source data). 

Where consuming systems are integrating data from this resource to their local system, they must also persist this identifier at the same time.

### Example

```json
    "identifier": {
      "system": "https://tools.ietf.org/html/rfc4122",
      "value": "123jkwndf-1234-dgdg-134dd-4f5e38aacdb0"
    },
```

---