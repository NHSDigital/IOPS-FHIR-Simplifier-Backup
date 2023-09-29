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
        <td>Mandatory</td>
        <td>1..1</td>
      </tr>
    </tbody>
</table>

Whether the request is a `plan` or `order`. 

 * `plan` represents an authorisation of a medication or medical device

 * `order` represents a prescription or issue of a medication/medical device

### Example

```json
 "intent" : "order",
```

---