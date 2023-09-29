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

`identifier` must be present within the task resource and the value must be a UUID.

### Example
```json
"identifier":  [
    {
        "system": "https://tools.ietf.org/html/rfc4122",
        "value": "5AC84C11-DB8B-44DA-8FCF-8980B3D13596"      
    }
],
```

### Comment
This is a business identifier, not a resource identifier.

---