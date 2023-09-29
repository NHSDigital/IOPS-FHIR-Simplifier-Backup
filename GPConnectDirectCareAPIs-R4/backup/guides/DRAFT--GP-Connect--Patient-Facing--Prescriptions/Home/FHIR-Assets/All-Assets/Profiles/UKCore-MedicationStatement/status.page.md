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

The status of the authorisation.

Use one of `active`, `completed` or `stopped`:

* `active` represents an active authorisation - used for active repeat medications/medical devices

* `stopped` represents an authorisation which has been discontinued, cancelled or stopped

* `complete` represents an authorisation which has run its course

For repeat and repeat dispensed the status refers to the status of the plan (the entire cycle of prescriptions).

For acute, the status refers to the status of the prescription issue.

### Example
```json
 "status": active
```

---