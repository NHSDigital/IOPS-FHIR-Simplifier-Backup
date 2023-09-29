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

Is needed for FHIR compliance reasons. The value must always be `order` in this use case.

### Example
```json
    "intent": "order",
```

---