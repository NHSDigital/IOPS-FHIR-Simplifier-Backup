### {{page-title}}

The assurance tool does not currently provide the output in the response body. Instead, it will send you an e-mail with two attachments.

1. A log file containing what the assurance tool received
2. A HTML file containing a report

The report will containing the following information:

* Date and time the report was generated
* Information pertanining to the rulset used for the validation
* A high-level summary containing number of files checked, passes and failures
* A results table by element and whether present.

### Example output

<table data-no-sort class="nhsd-!t-margin-bottom-7">
    <thead>
        <th>Element required for MVP</th>
        <th>Element present in Test Message</th>
    </thead>
    <tbody>
        <tr>
            <td>id</td>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-green">true</span></td>
        </tr>
        <tr>
            <td>status</td>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-red">false</span></td>
        </tr>
        <tr>
            <td>intent</td>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-red">false</span></td>
        </tr>
        <tr>
            <td>category</td>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-green">true</span></td>
        </tr>
        <tr>
            <td>priority</td>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-green">true</span></td>
        </tr>
        <tr>
            <td>medication</td>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-green">true</span></td>
        </tr>
        <tr>
            <td>subject</td>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-green">true</span></td>
        </tr>
    </tbody>
</table>