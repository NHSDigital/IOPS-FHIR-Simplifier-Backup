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
        <td>Annotation</td>
        <td>Optional</td>
        <td>0..*</td>
      </tr>
    </tbody>
</table>

Use when the prescriber wishes to provide supporting textual information to the dispenser.

### Example

```json
      "note" : [ {
        "authorString" : "Patient",
        "text" : "Ran out of previous prescription"
      } ]
```

---