## Element: `recorder` <span class="mro-circle mandatory" title="Mandatory"></span>

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>Recommendation</strong>: use <code>recorder</code> as a required business element for most MVP implementations to be used as an additional point of contact for the pharmacy, together with the requester for any queries related to the medication request.
</div>

### Requester and Recorder combination examples

<table data-responsive>
    <thead>
        <tr>
            <th>Scenario</th>
            <th class="text-center">Requester</th>
            <th class="text-center">Recorder</th>
        </tr>
    </thead>
    <tbody>
        <!-- Fred - new meds -->
        <tr>
            <td>Prescibing clinician <strong class="bg-success">Fred</strong> is requesting new medication</td>
            <td class="bg-success text-center"><strong>Fred</strong></td>
            <td class="bg-success text-center"><strong>Fred</strong></td>
        </tr>
        <!-- Fred - reorder -->
        <tr>
            <td>Prescibing clinician <strong class="bg-success">Fred</strong> is re-ordering previous medication he previously prescribed</td>
            <td class="bg-success text-center"><strong>Fred</strong></td>
            <td class="bg-success text-center"><strong>Fred</strong></td>
        </tr>
        <!-- Jane - reordering meds Fred previous prescribed - no changes -->
        <tr>
            <td>Prescibing clinician <strong class="bg-info">Jane</strong> is re-ordering previous medication, without any clinical changes, that <strong class="bg-success">Fred</strong> previously prescribed</td>
            <td class="bg-success text-center"><strong>Fred</strong></td>
            <td class="bg-info text-center"><strong>Jane</strong></td>
        </tr>
        <!-- Jane - reordering meds Fred previous prescribed - with changes -->
        <tr>
            <td>Prescibing clinician <strong class="bg-info">Jane</strong> is re-ordering previous medication that <strong class="bg-success">Fred</strong> previously prescribed, with clinical changes</td>
            <td class="bg-info text-center"><strong>Jane</strong></td>
            <td class="bg-info text-center"><strong>Jane</strong></td>
        </tr>
        <!-- Rodger - ordering meds prescribed by Fred -->
        <tr>
            <td>Nurse <strong class="bg-danger">Rodger</strong> is ordering medication prescribed by <strong class="bg-success">Fred</strong></td>
            <td class="bg-success text-center"><strong>Fred</strong></td>
            <td class="bg-danger text-center"><strong>Rodger</strong></td>
        </tr>
        <!-- Sally - re-ordering previous meds prescribed by Fred -->
        <tr>
            <td>Pharmacy technical <strong class="bg-warning">Sally</strong> is re-ordering medication prescribed by <strong class="bg-success">Fred</strong></td>
            <td class="bg-success text-center"><strong>Fred</strong></td>
            <td class="bg-warning text-center"><strong>Sally</strong></td>
        </tr>
    </tbody>
</table>

---