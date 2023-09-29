## {{page-title}}

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">

-  <b>Safe to display to patient / citizen</b> - With a safety rating of 'High', 'Medium' or 'Low'.

-  <b>Useful to display to patient / citizen</b> - With a recommendation of 'Recommended' or 'Not recommended'.

For example, the element 'Id’ has a safety rating of ‘High’, meaning it can be shown via Patient Facing Services (PFS). However, we believe it may not be useful to display 'Not Recommended' for the patient / citizen. It’s worth noting, there are elements that will have no meaning or have any merit in being displayed such as ‘Id’. For example, some elements are just entities that link data together.

For further information on the labelling please visit {{pagelink:Home/Introduction/How-to-use-the-implementation-guide/Data-model-labels-used-within-this-guidance.page.md}}.
</div>

### DiagnosticReport

<table data-responsive>
    <thead>
        <tr>
            <th>Element</th>
            <th data-no-sort>Safe to display to patient / citizen</th>
            <th data-no-sort>Useful to display to patient / citizen</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>id</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not useful"></span></td>
        </tr>
        <tr>
            <td>meta.profile</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not useful"></span></td>
        </tr>
        <tr>
            <td>identifier</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not useful"></span></td>
        </tr>
        <tr>
            <td>basedOn</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not useful"></span></td>
        </tr>
        <tr>
            <td>status</td>
            <td><span class="fas fa-exclamation-circle text-warning fa-lg" title="Use with caution"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>category</td>
            <td><span class="fas fa-exclamation-circle text-warning fa-lg" title="Use with caution"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>code</td>
            <td><span class="fas fa-exclamation-circle text-warning fa-lg" title="Use with caution"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>subject</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not useful"></span></td>
        </tr>
        <tr>
            <td>context</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not useful"></span></td>
        </tr>
        <tr>
            <td>issued</td>
            <td><span class="fas fa-exclamation-circle text-warning fa-lg" title="Use with caution"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>performer</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not useful"></span></td>
        </tr>
        <tr>
            <td>specimen</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>result</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>codedDiagnosis</td>
            <td><span class="fas fa-exclamation-circle text-warning fa-lg" title="Use with caution"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>conclusion</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
    </tbody>
</table>

---

### Specimen

<table data-responsive>
    <thead>
        <tr>
            <th>Element</th>
            <th data-no-sort>Safe to display to patient / citizen</th>
            <th data-no-sort>Useful to display to patient / citizen</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>id</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not useful"></span></td>
        </tr>
        <tr>
            <td>meta.profile</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not useful"></span></td>
        </tr>
        <tr>
            <td>accessionIdentifier</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not useful"></span></td>
        </tr>
        <tr>
            <td>status</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not useful"></span></td>
        </tr>
        <tr>
            <td>type</td>
            <td><span class="fas fa-exclamation-circle text-warning fa-lg" title="Use with caution"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>subject</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not useful"></span></td>
        </tr>
        <tr>
            <td>receivedTime</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not useful"></span></td>
        </tr>
        <tr>
            <td>collection</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not useful"></span></td>
        </tr>
        <tr>
            <td>collection.extension[fastingStatus]</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>collection.collector</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not useful"></span></td>
        </tr>
        <tr>
            <td>collection.collected</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>collection.quantity</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not useful"></span></td>
        </tr>
        <tr>
            <td>collection.bodysite</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>note</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
    </tbody>
</table>

---

### Observation - test group header

<table data-responsive>
    <thead>
        <tr>
            <th>Element</th>
            <th data-no-sort>Safe to display to patient / citizen</th>
            <th data-no-sort>Useful to display to patient / citizen</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>id</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not useful"></span></td>
        </tr>
        <tr>
            <td>meta.profile</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not useful"></span></td>
        </tr>
        <tr>
            <td>identifier</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not useful"></span></td>
        </tr>
        <tr>
            <td>status</td>
            <td><span class="fas fa-exclamation-circle text-warning fa-lg" title="Use with caution"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>code</td>
            <td><span class="fas fa-exclamation-circle text-warning fa-lg" title="Use with caution"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>subject</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not useful"></span></td>
        </tr>
        <tr>
            <td>context</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not useful"></span></td>
        </tr>
        <tr>
            <td>effective[x]</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>issued</td>
            <td><span class="fas fa-exclamation-circle text-warning fa-lg" title="Use with caution"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>performer</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not useful"></span></td>
        </tr>
        <tr>
            <td>interpretation</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>comment</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>specimen</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>related</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not useful"></span></td>
        </tr>
    </tbody>
</table>

---

### Observation - test result

<table data-responsive>
    <thead>
        <tr>
            <th>Element</th>
            <th data-no-sort>Safe to display to patient / citizen</th>
            <th data-no-sort>Useful to display to patient / citizen</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>id</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not useful"></span></td>
        </tr>
        <tr>
            <td>meta.profile</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not useful"></span></td>
        </tr>
        <tr>
            <td>identifier</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not useful"></span></td>
        </tr>
        <tr>
            <td>status</td>
            <td><span class="fas fa-exclamation-circle text-warning fa-lg" title="Use with caution"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>category</td>
            <td><span class="fas fa-exclamation-circle text-warning fa-lg" title="Use with caution"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>code</td>
            <td><span class="fas fa-exclamation-circle text-warning fa-lg" title="Use with caution"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>subject</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not useful"></span></td>
        </tr>
        <tr>
            <td>context</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not useful"></span></td>
        </tr>
        <tr>
            <td>effective[x]</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>issued</td>
            <td><span class="fas fa-exclamation-circle text-warning fa-lg" title="Use with caution"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>performer</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not useful"></span></td>
        </tr>
        <tr>
            <td>value[x]</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>dataAbsentReason</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>interpretation</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>comment</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>bodysite</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>method</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>specimen</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>referenceRange</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>related</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not useful"></span></td>
        </tr>
    </tbody>
</table>

---

### Observation - filing Comments 

<table data-responsive>
    <thead>
        <tr>
            <th>Element</th>
            <th data-no-sort>Safe to display to patient / citizen</th>
            <th data-no-sort>Useful to display to patient / citizen</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>id</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not useful"></span></td>
        </tr>
        <tr>
            <td>meta.profile</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not useful"></span></td>
        </tr>
        <tr>
            <td>identifier</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not useful"></span></td>
        </tr>
        <tr>
            <td>status</td>
            <td><span class="fas fa-exclamation-circle text-warning fa-lg" title="Use with caution"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>code</td>
            <td><span class="fas fa-exclamation-circle text-warning fa-lg" title="Use with caution"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>subject</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not useful"></span></td>
        </tr>
        <tr>
            <td>context</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not useful"></span></td>
        </tr>
        <tr>
            <td>effective[x]</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>issued</td>
            <td><span class="fas fa-exclamation-circle text-warning fa-lg" title="Use with caution"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>performer</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not useful"></span></td>
        </tr>
        <tr>
            <td>value[x]</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not useful"></span></td>
        </tr>
        <tr>
            <td>comment</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>related</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not useful"></span></td>
        </tr>
    </tbody>
</table>

---

### ProcedureRequest

<table data-responsive>
    <thead>
        <tr>
            <th>Element</th>
            <th data-no-sort>Safe to display to patient / citizen</th>
            <th data-no-sort>Useful to display to patient / citizen</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>id</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not useful"></span></td>
        </tr>
        <tr>
            <td>meta.profile</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not useful"></span></td>
        </tr>
        <tr>
            <td>identifier</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not useful"></span></td>
        </tr>
        <tr>
            <td>status</td>
            <td><span class="fas fa-exclamation-circle text-warning fa-lg" title="Use with caution"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>intent</td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not advised"></span></td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not useful"></span></td>
        </tr>
        <tr>
            <td>code</td>
            <td><span class="fas fa-exclamation-circle text-warning fa-lg" title="Use with caution"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>subject</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not useful"></span></td>
        </tr>
        <tr>
            <td>performer</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not useful"></span></td>
        </tr>
        <tr>
            <td>requester</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>reasonCode</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>reasonReference</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>note</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
    </tbody>
</table>

---