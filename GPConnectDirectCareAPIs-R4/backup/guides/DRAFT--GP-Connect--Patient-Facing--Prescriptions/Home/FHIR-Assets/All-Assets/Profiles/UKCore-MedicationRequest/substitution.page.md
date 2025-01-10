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
        <td>BackboneElement</td>
        <td>Required</td>
        <td>1..1</td>
      </tr>
    </tbody>
</table>

UK Core has profiled this element as mandatory and must have a default boolean value of `false` to denote substitution is not allowed.

### Example
```json
    "substitution": {
        "allowedBoolean": false
    }
```