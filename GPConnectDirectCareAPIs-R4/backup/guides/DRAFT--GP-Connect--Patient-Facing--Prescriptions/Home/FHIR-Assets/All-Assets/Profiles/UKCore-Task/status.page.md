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
        <td>1..1</td>
      </tr>
    </tbody>
</table>


The status of the Task must be provided and updated as the Task passes through the GP system workflow.

<table data-responsive>
    <thead>
        <tr>
            <th>Status</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>requested</td>
            <td>Repeat request has been submitted to the GP practice but processing has not started.</td>
        </tr>
        <tr>
            <td>accepted</td>
            <td>The request has passed auto-system checks, e.g. valid patient, practice, etc. and is now pending user processing.
</td>
        </tr>
        <tr>
            <td>rejected</td>
            <td>The request will not be actioned. The business reason will be conveyed in ‘statusReason’, e.g. patient not known at the practice.</td>
        </tr>
        <tr>
            <td>cancelled</td>
            <td>The patient cancelled the request before it was actioned.</td>
        </tr>
        <tr>
            <td>in-progress</td>
            <td>The request has been processed by a prescription clerk and is awaiting confirmation/authorisation (signing) by a prescriber.</td>
        </tr>
        <tr>
            <td>completed</td>
            <td>The prescription has been authorised/signed. Refer to the EPS state model for the dispensing status.</td>
        </tr>
        <tr>
            <td>failed</td>
            <td>A prescription has not been authorised. The business reason will be conveyed in ‘statusReason’, e.g. on clinical grounds.</td>
        </tr>
      </tbody>
</table>

### Example
```json
 "status": completed
```

---