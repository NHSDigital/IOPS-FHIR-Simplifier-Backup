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

A code specifying the current state of the order. Generally, this will be active or completed state.

<table data-responsive>
    <thead>
        <tr>
            <th>code</th>
            <th>Definition</th>
        </tr>
    </thead>
    <tbody>
      <tr>
        <td>active</td>
        <td>Represents an active authorisation - used for active medications/medical devices.</td>
      </tr>
      <tr>
        <td>stopped</td>
        <td>Represents an authorisation which has been discontinued, cancelled or stopped.</td>
      </tr>
      <tr>
        <td>completed</td>
        <td>Represents an authorisation which has run its course.</td>
      </tr>
    </tbody>
</table>

For MedicationRequest instances where intent is set to plan:
*   For repeats and repeat dispensed the status refers to the status of the plan (the entire cycle of prescriptions).
*   For acutes the status refers to the status of the prescription issue.

For MedicationRequest instances where intent is set to order:

*  The status refers to the status of the prescription issue.

### Example
``` json
  "status" : "active",
```

---