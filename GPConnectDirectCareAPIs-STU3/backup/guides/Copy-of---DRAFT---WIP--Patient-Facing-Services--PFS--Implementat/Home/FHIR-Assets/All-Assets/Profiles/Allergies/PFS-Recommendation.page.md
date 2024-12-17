## {{page-title}}

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">

-  <b>Safe to display to patient/citizen</b> - With a safety rating of 'High', 'Medium' or 'Low'.

-  <b>Useful to display to patient/citizen</b> - With a recommendation of 'Recommended' or 'Not recommended'.

For example, the element 'Id’ has a safety rating of ‘High’, meaning it can be shown via Patient Facing Services (PFS). However, we believe it may not be useful to display 'Not Recommended' for the patient/citizen. It’s worth noting, there are elements that will have no meaning or have any merit in being displayed such as ‘Id’. For example, some elements are just entities that link data together.

For further information on the labelling, visit {{pagelink:Home/Introduction/How-to-use-the-implementation-guide/Data-model-labels-used-within-this-guidance.page.md}}.
</div>

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
            <td>extension[encounter]</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>extension[allergyEnd]</td>
            <td><span class="fas fa-exclamation-circle text-warning fa-lg" title="Use with caution"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>extension[allergyEnd].endDate</td>
            <td><span class="fas fa-exclamation-circle text-warning fa-lg" title="Use with caution"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>extension[allergyEnd].endReason</td>
            <td><span class="fas fa-exclamation-circle text-warning fa-lg" title="Use with caution"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>identifier</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not useful"></span></td>
        </tr>
        <tr>
            <td>clinicalStatus</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>verificationStatus</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not useful"></span></td>
        </tr>
        <tr>
            <td>type</td>
            <td><span class="fas fa-exclamation-circle text-warning fa-lg" title="Use with caution"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>category</td>
            <td><span class="fas fa-exclamation-circle text-warning fa-lg" title="Use with caution"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>criticality</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>code</td>
            <td><span class="fas fa-exclamation-circle text-warning fa-lg" title="Use with caution"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>patient</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not useful"></span></td>
        </tr>
        <tr>
            <td>onset.DateTime</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>assertedDate</td>
            <td><span class="fas fa-exclamation-circle text-warning fa-lg" title="Use with caution"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>recorder</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>asserter</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>lastOccurence</td>
            <td><span class="fas fa-exclamation-circle text-warning fa-lg" title="Use with caution"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>note</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>reaction.manifestation</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not useful"></span></td>
        </tr>
        <tr>
            <td>reaction.description</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>reaction.severity</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>reaction.exposureRoute</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
    </tbody>
</table>

---