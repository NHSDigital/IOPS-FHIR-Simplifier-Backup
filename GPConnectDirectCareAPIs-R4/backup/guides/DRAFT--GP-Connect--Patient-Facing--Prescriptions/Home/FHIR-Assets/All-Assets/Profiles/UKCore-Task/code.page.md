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
        <td>Required</td>
        <td>0..1</td>
      </tr>
    </tbody>
</table>

The code indicates the action to perform on the focus resource. 

It is a [Snomed CT](http://snomed.info/sct) and must always be set `Renewal of prescription`.


<table data-responsive>
    <thead>
        <tr>
            <th>Snomed CT</th>
            <th>Display</th>
        </tr>
    </thead>
    <tbody>
      <tr>
        <td>103742009</td>
        <td>Renewal of prescription</td>
      </tr>
    </tbody>
</table>

### Example
```json
"code" : {
    "coding" : [ {
      "system" : "http://snomed.info/sct",
      "code" : 103742009,
      "display" : "Renewal of prescription"
    } ]
  },
```

---