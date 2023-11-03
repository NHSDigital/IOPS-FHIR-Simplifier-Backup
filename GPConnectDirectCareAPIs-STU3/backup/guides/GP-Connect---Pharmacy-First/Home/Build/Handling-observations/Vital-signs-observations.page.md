## {{page-title}}

The [Community Pharmacy Standard v3](https://prsb2.vercel.app/page/community-pharmacy-standardv3) stipulates the following items that could be sent.

<br />

The table below outlines which of the items listed under Examination findings &rarr; Observations int he PRSB CP spec above, and whether or not this specification supports them.

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <b>Note</b>: Text enclosed in curly braces <code>{ ... }</code> is called an annotation.
    <br />
    Refer to sub-section 6 in <a href="https://ucum.org/ucum#section-Character-Set-and-Lexical-Rules">2.1 Character set and lexical rules</a> of the UCUM specificaiton.
</div>

<table data-responsive class="nhsd-!t-margin-bottom-6 nhsd-!t-margin-top-6">
    <thead>
        <th data-no-sort>Observation</th>
        <th data-no-sort>Expected value</th>
        <th data-no-sort  class="nhsd-t-text-align-center">Supported</th>
    </thead>
    <tbody>
        <tr>
            <td>Height / length</td>
            <td><ul><li>UCUM: <code>cm</code></li><li>UCUM: <code>[in_i]</code></li></ul></td>
            <td class="nhsd-t-text-align-center">Yes</td>
        </tr>
        <tr>
            <td>Weight</td>
            <td><ul><li>UCUM: <code>g</code></li><li>UCUM: <code>kg</code></li><li>UCUM: <code>[lb_av]</code></li></ul></td>
            <td class="nhsd-t-text-align-center">Yes</td>
        </tr>
        <tr>
            <td>Body mass index (BMI)</td>
            <td>UCUM: <code>kg/m2</code></td>
            <td class="nhsd-t-text-align-center">Yes</td>
        </tr>
        <tr>
            <td>Blood pressure - Systolic</td>
            <td>UCUM: <code>mm[Hg]</code></td>
            <td class="nhsd-t-text-align-center">Yes</td>
        </tr>
        <tr>
            <td>Blood pressure - Diastolic</td>
            <td>UCUM: <code>mm[Hg]</code></td>
            <td class="nhsd-t-text-align-center">Yes</td>
        </tr>
        <tr>
            <td>Heart rate</td>
            <td>UCUM: <code>{beats}/min</code></td>
            <td class="nhsd-t-text-align-center">Yes</td>
        </tr>
        <tr>
            <td>Temperature</td>
            <td><ul><li>UCUM: <code>Cel</code></li><li>UCUM: <code>[degF]</code></li></ul></td>
            <td class="nhsd-t-text-align-center">Yes</td>
        </tr>
        <tr>
            <td>Oxygen saturation</td>
            <td>UCUM: <code>%</code></td>
            <td class="nhsd-t-text-align-center">No</td>
        </tr>
        <tr>
        <tr>
            <td>Pain score</td>
            <td>UCUM: <code>{ScoreOf}</code></td>
            <td class="nhsd-t-text-align-center">No</td>
        </tr>
        <tr>
            <td>Level of consciousness</td>
            <td>CodeSystem: <a href="https://fhir.hl7.org.uk/STU3/ValueSet/CareConnect-ACVPU-1">CareConnect-ACVPU-1</a></td>
            <td class="nhsd-t-text-align-center">No</td>
        </tr>
        <tr>
            <td>Respiratory rate</td>
            <td>UCUM: <code>{breaths}/min</code></td>
            <td class="nhsd-t-text-align-center">No</td>
        </tr>
        <tr>
            <td>Air and oxygen</td>
            <td>UCUM: <code>%</code></td>
            <td class="nhsd-t-text-align-center">No</td>
        </tr>
        <tr>
            <td>NEWS2</td>
            <td>UCUM: <code>{ScoreOf}</code></td>
            <td class="nhsd-t-text-align-center">No</td>
        </tr>
    </tbody>
</table>

---
