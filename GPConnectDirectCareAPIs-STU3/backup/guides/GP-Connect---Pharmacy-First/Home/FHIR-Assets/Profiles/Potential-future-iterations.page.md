## {{page-title}}

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
    <b>Important</b>: Messages containing the profiles below or any other profiles that are not in "Iteration 1" (above) then the <b>entire ITK3 message MUST BE rejected</b> by the consumer (receiving) system, with the ITK3 acknowledgement response code <b><code>20009</code> - Payload validation failure.</b>
</div>

The following profiles are required by the Professional Records Standards Body; however, additional guidance is needed before they can be included

There is also potential overlap with BaRS - hence why out of scope for Iterations 1 and 2.

<table data-responsive>
    <thead>
        <tr>
            <th data-no-sort>Profile</th>
            <th data-no-sort>Source</th>
            <th data-no-sort>Cardinality</th>
            <th data-no-sort>Optionality</th>
        </tr>
    </thead>
    <tbody>
        <!-- GPConnect-Appointment-1 -->
        <tr>
            <td class="nhsd-t-body">
                {{pagelink:Home/FHIR-Assets/All-assets/Profiles/Profile--GPConnect-Appointment-1}}
            </td>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-green">PRSB</span></td>
            <td class="nhsd-t-body"><code>0..?</code></td>
            <td class="nhsd-t-body"><span class="mro-circle unknown"></span> TBC</td>
        </tr>
        <!-- CareConnect-Flag-1 -->
        <tr>
            <td class="nhsd-t-body">
                {{pagelink:Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-Flag-1}}
            </td>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-green">PRSB</span></td>
            <td class="nhsd-t-body"><code>0..*</code></td>
            <td class="nhsd-t-body"><span class="mro-circle unknown"></span> TBC</td>
        </tr>
        <!-- CareConnect-GPC-Procedure-1 -->
        <tr>
            <td class="nhsd-t-body">
                {{pagelink:Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-Procedure-1}}
            </td>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-green">PRSB</span></td>
            <td class="nhsd-t-body"><code>0..?</code></td>
            <td class="nhsd-t-body"><span class="mro-circle unknown"></span> TBC</td>
        </tr>        
        <!-- CareConnect-GPC-ReferralRequest-1 -->
        <tr>
            <td class="nhsd-t-body">
                {{pagelink:Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-GPC-ReferralRequest-1}}
            </td>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-green">PRSB</span></td>
            <td class="nhsd-t-body"><code>0..?</code></td>
            <td class="nhsd-t-body"><span class="mro-circle unknown"></span> TBC</td>
        </tr>
    </tbody>
</table>