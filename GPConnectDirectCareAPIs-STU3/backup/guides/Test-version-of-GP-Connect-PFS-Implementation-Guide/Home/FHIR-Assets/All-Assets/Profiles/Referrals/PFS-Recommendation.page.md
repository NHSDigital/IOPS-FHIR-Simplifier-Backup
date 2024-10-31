## {{page-title}}

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">

-  <b>Safe to display to patient / citizen</b> - With a safety rating of 'High', 'Medium' or 'Low'.

-  <b>Useful to display to patient / citizen</b> - With a recommendation of 'Recommended' or 'Not recommended'.

For example, the element 'Id’ has a safety rating of ‘High’, meaning it can be shown via Patient Facing Services (PFS). However, we believe it may not be useful to display 'Not Recommended' for the patient / citizen. It’s worth noting, there are elements that will have no meaning or have any merit in being displayed such as ‘Id’. For example, some elements are just entities that link data together.

For further information on the labelling please visit {{pagelink:Home/Introduction/How-to-use-the-implementation-guide/Data-model-labels-used-within-this-guidance.page.md}}.
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
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not advised"></span></td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not useful"></span></td>
        </tr>
        <tr>
            <td>intent</td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not advised"></span></td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not useful"></span></td>
        </tr>
        <tr>
            <td>priority</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>serviceRequested</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
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
            <td>authoredOn</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>requester</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not useful"></span></td>
        </tr>
        <tr>
            <td>requester.agent</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>requester.onBehalfOf</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not useful"></span></td>
        </tr>
        <tr>
            <td>specialty</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>recipient</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>reasonCode</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>description</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>supportingInfo</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not useful"></span></td>
        </tr>
        <tr>
            <td>note</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
    </tbody>
</table>

---