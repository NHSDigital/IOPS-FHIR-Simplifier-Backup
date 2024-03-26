## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle mandatory" title="Mandatory"></span> Mandatory


<h5><ins>Guidance</ins></h5>

The person who entered the record on the system. The table below outlines `requester` and `recorder` combinations for clarity.

<table data-responsive class="nhsd-!t-margin-bottom-6">
    <thead>
        <tr>
            <th data-no-sort>Scenario</th>
            <th data-no-sort class="text-center">Requester</th>
            <th data-no-sort class="text-center">Recorder</th>
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

<h5><ins>Example</ins></h5>

```xml
<recorder>
    <identifier>
        <system value="https://fhir.hl7.org.uk/Id/gmc-number" />
        <value value="0054272" />
    </identifier>
 </recorder>
```

---