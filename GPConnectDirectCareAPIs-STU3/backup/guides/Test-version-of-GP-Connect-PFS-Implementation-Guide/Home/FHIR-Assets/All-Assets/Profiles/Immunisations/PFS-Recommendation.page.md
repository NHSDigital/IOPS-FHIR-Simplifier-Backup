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
            <td>extension[parentPresent]</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>extension[recordedDate]</td>
            <td><span class="fas fa-exclamation-circle text-warning fa-lg" title="Use with caution"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>extension[vaccinationProcedure]</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>identifier</td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not advised"></span></td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not useful"></span></td>
        </tr>
        <tr>
            <td>status</td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not advised"></span></td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not useful"></span></td>
        </tr>
        <tr>
            <td>notGiven</td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not advised"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>vaccineCode</td>
            <td><span class="fas fa-exclamation-circle text-warning fa-lg" title="Use with caution"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>patient</td>
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
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>primarySource</td>
            <td><span class="fas fa-exclamation-circle text-warning fa-lg" title="Use with caution"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>reportOrigin</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>location</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not useful"></span></td>
        </tr>
        <tr>
            <td>manufacturer</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>lotNumber</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>expirationDate</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not useful"></span></td>
        </tr>
        <tr>
            <td>site</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not useful"></span></td>
        </tr>
        <tr>
            <td>route</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not useful"></span></td>
        </tr>
        <tr>
            <td>doseQuantity</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>practitioner</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not useful"></span></td>
        </tr>
        <tr>
            <td>practitioner.role</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not useful"></span></td>
        </tr>
        <tr>
            <td>practitioner.actor</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>note</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>explanation.reason</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>explanation.reasonNotGiven</td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not advised"></span></td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not useful"></span></td>
        </tr>
        <tr>
            <td>vaccinationProtocol</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not useful"></span></td>
        </tr>
        <tr>
            <td>vaccinationProtocol.doseSequence</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not useful"></span></td>
        </tr>
        <tr>
            <td>vaccinationProtocol.description</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not useful"></span></td>
        </tr>
        <tr>
            <td>vaccinationProtocol.seriesDoses</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not useful"></span></td>
        </tr>
        <tr>
            <td>vaccinationProtocol.targetDisease</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not useful"></span></td>
        </tr>
        <tr>
            <td>vaccinationProtocol.doseStatus</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
            <td><span class="fas fa-times-circle text-danger fa-lg" title="Not useful"></span></td>
        </tr>
    </tbody>
</table>

---