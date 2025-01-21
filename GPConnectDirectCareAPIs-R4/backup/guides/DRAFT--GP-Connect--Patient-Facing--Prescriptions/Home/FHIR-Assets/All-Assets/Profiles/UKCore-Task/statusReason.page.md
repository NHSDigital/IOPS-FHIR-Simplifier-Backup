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
        <td>string</td>
        <td>optional, only used to notify the patient of rejection reasons</td>
        <td>0:1</td>
      </tr>
    </tbody>
</table>

This will be free text containing the rejection reason to be shown back to the patient. 

### Example
```json
"statusReason": {
    "text": "No longer suitable, please contact GP to organise an appointment"
},
```

---