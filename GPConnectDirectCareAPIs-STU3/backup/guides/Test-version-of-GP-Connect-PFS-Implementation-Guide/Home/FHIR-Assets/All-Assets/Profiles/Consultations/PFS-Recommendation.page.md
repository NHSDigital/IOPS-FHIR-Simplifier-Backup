## {{page-title}}

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">

-  <b>Safe to display to patient / citizen</b> - With a safety rating of 'High', 'Medium' or 'Low'.

-  <b>Useful to display to patient / citizen</b> - With a recommendation of 'Recommended' or 'Not recommended'.

For example, the element 'Id’ has a safety rating of ‘High’, meaning it can be shown via Patient Facing Services (PFS). However, we believe it may not be useful to display 'Not Recommended' for the patient / citizen. It’s worth noting, there are elements that will have no meaning or have any merit in being displayed such as ‘Id’. For example, some elements are just entities that link data together.

For further information on the labelling please visit {{pagelink:Home/Introduction/How-to-use-the-implementation-guide/Data-model-labels-used-within-this-guidance.page.md}}.
</div>

### Encounter

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
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not advised"></span></td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not useful"></span></td>
        </tr>
        <tr>
            <td>type</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>subject</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not useful"></span></td>
        </tr>
        <tr>
            <td>participant</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>period</td>
            <td><span class="fas fa-exclamation-circle text-warning fa-lg" title="Use with caution"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>length</td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not advised"></span></td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not useful"></span></td>
        </tr>
        <tr>
            <td>location</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>serviceProvider</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
    </tbody>
</table>

---

### List (Common)

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
            <td>status</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not useful"></span></td>
        </tr>
        <tr>
            <td>mode</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not useful"></span></td>
        </tr>
        <tr>
            <td>subject</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not useful"></span></td>
        </tr>
        <tr>
            <td>encounter</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not useful"></span></td>
        </tr>
        <tr>
            <td>date</td>
            <td><span class="fas fa-exclamation-circle text-warning fa-lg" title="Use with caution"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>orderedBy</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not useful"></span></td>
        </tr>
    </tbody>
</table>

---

### List (Consultation)

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
            <td>title</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>code</td>
            <td><span class="fas fa-exclamation-circle text-warning fa-lg" title="Use with caution"></span></td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not useful"></span></td>
        </tr>
        <tr>
            <td>entry</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not useful"></span></td>
        </tr>
    </tbody>
</table>

---

### List (Topic)

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
            <td>extension(relatedProblemHeader)</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>title</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>code</td>
            <td><span class="fas fa-exclamation-circle text-warning fa-lg" title="Use with caution"></span></td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not useful"></span></td>
        </tr>
        <tr>
            <td>entry</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not useful"></span></td>
        </tr>
    </tbody>
</table>

---

### List (Heading)

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
            <td>title</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>code</td>
            <td><span class="fas fa-exclamation-circle text-warning fa-lg" title="Use with caution"></span></td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not useful"></span></td>
        </tr>
        <tr>
            <td>entry</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not useful"></span></td>
        </tr>
    </tbody>
</table>

---