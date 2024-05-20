## {{page-title}}

<table data-responsive>
    <thead>
        <tr>
            <th>Element</th>
            <th data-no-sort>Use</th>
            <th data-no-sort>CareConnect (STU3)</th>
            <th data-no-sort>UK Core (R4)</th>
        </tr>
    </thead>
    <tbody>
        <!-- id -->
        <tr>
            <td>id</td>
            <td><span class="mro-circle optional" title="Optional"></span></td>
            <td><i class="fas fa-check text-success"></i></td>
            <td><i class="fas fa-check text-success"></i></td>
        </tr>
        <!-- meta.versionId -->
        <tr>
            <td>meta.versionId</td>
            <td><span class="mro-circle optional" title="Optional"></span></td>
            <td><i class="fas fa-check text-success"></i></td>
            <td><i class="fas fa-check text-success"></i></td>
        </tr>
        <!-- meta.lastUpdated -->
        <tr>
            <td>meta.lastUpdated</td>
            <td><span class="mro-circle optional" title="Optional"></span></td>
            <td><i class="fas fa-check text-success"></i></td>
            <td><i class="fas fa-check text-success"></i></td>
        </tr>
        <!-- meta.profile -->
        <tr>
            <td>meta.profile</td>
            <td><span class="mro-circle mandatory" title="Mandatory"></span></td>
            <td><i class="fas fa-check text-success"></i></td>
            <td><i class="fas fa-check text-success"></i></td>
        </tr>
        <!-- meta.security -->
        <tr>
            <td>meta.security</td>
            <td><span class="mro-circle optional" title="Optional"></span></td>
            <td><i class="fas fa-check text-success"></i></td>
            <td><i class="fas fa-check text-success"></i></td>
        </tr>
        <!-- meta.tag -->
        <tr>
            <td>meta.tag</td>
            <td><span class="mro-circle optional" title="Optional"></span></td>
            <td><i class="fas fa-check text-success"></i></td>
            <td><i class="fas fa-check text-success"></i></td>
        </tr>
        <!-- extension(lastIssueDate) -->
        <tr>
            <td>extension(lastIssueDate)</td>
            <td><span class="mro-circle required" title="Required"></span></td>
            <td><i class="fas fa-check text-success"></i></td>
            <td><i class="fas fa-exclamation text-warning" title="Renamed to 'medicationStatementLastIssued' in UK Core"></i></td>
        </tr>
        <!-- extension(changeSummary) -->
        <tr>
            <td>extension(changeSummary)</td>
            <td><span class="mro-circle optional" title="Optional"></span></td>
            <td><i class="fas fa-times text-danger"></i></td>
            <td><i class="fas fa-times text-danger"></i></td>
        </tr>
        <!-- extension(prescribingAgency) -->
        <tr>
            <td>extension(prescribingAgency)</td>
            <td><span class="mro-circle mandatory" title="Mandatory"></span></td>
            <td><i class="fas fa-times text-danger"></i></td>
            <td><i class="fas fa-exclamation text-warning" title="Renamed to 'medicationPrescribingOrganisation' in UK Core"></i></td>
        </tr>
        <!-- extension(dosageLastChanged) -->
        <tr>
            <td>extension(dosageLastChanged)</td>
            <td><span class="mro-circle optional" title="Optional"></span></td>
            <td><i class="fas fa-times text-danger"></i></td>
            <td><i class="fas fa-times text-danger"></i></td>
        </tr>
        <!-- extension(medicationTradeFamily) --> 
        <tr>
            <td>extension(medicationTradeFamily)</td>
            <td><span class="mro-circle optional" title="Optional"></span></td>
            <td><i class="fas fa-check text-success"></i></td>
            <td><i class="fas fa-times text-danger"></i></td>
        </tr>
        <!-- identifier -->
        <tr>
            <td>identifier</td>
            <td><span class="mro-circle mandatory" title="Mandatory"></span></td>
            <td><i class="fas fa-check text-success"></i></td>
            <td><i class="fas fa-check text-success"></i></td>
        </tr>
        <!-- basedOn -->
        <tr>
            <td>basedOn</td>
            <td><span class="mro-circle mandatory" title="Mandatory"></span></td>
            <td><i class="fas fa-check text-success"></i></td>
            <td><i class="fas fa-check text-success"></i></td>
        </tr>
        <!-- partOf -->
        <tr>
            <td>partOf</td>
            <td><span class="mro-circle optional" title="Optional"></span></td>
            <td><i class="fas fa-check text-success"></i></td>
            <td><i class="fas fa-check text-success"></i></td>
        </tr>
        <!-- context -->
        <tr>
            <td>context</td>
            <td><span class="mro-circle required" title="Required"></span></td>
            <td><i class="fas fa-check text-success"></i></td>
            <td><i class="fas fa-check text-success"></i></td>
        </tr>
        <!-- status -->
        <tr>
            <td>status</td>
            <td><span class="mro-circle mandatory" title="Mandatory"></span></td>
            <td><i class="fas fa-check text-success"></i></td>
            <td><i class="fas fa-check text-success"></i></td>
        </tr>
        <!-- category -->
        <tr>
            <td>category</td>
            <td><span class="mro-circle required" title="Required"></span></td>
            <td><i class="fas fa-check text-success"></i></td>
            <td><i class="fas fa-check text-success"></i></td>
        </tr>
        <!-- medicationReference -->
        <tr>
            <td>medicationReference</td>
            <td><span class="mro-circle mandatory" title="Mandatory"></span></td>
            <td><i class="fas fa-check text-success"></i></td>
            <td><i class="fas fa-check text-success"></i></td>
        </tr>
        <!-- effective[x] -->
        <tr>
            <td>effective[x]</td>
            <td><span class="mro-circle required" title="Required"></span></td>
            <td><i class="fas fa-check text-success"></i></td>
            <td><i class="fas fa-check text-success"></i></td>
        </tr>
        <!-- dateAsserted -->
        <tr>
            <td>dateAsserted</td>
            <td><span class="mro-circle mandatory" title="Mandatory"></span></td>
            <td><i class="fas fa-check text-success"></i></td>
            <td><i class="fas fa-check text-success"></i></td>
        </tr>
        <!-- informationSource -->
        <tr>
            <td>informationSource</td>
            <td><span class="mro-circle required" title="Required"></span></td>
            <td><i class="fas fa-check text-success"></i></td>
            <td><i class="fas fa-check text-success"></i></td>
        </tr>
        <!-- subject -->
        <tr>
            <td>subject</td>
            <td><span class="mro-circle mandatory" title="Mandatory"></span></td>
            <td><i class="fas fa-check text-success"></i></td>
            <td><i class="fas fa-check text-success"></i></td>
        </tr>
        <!-- derivedFrom -->
        <tr>
            <td>derivedFrom</td>
            <td><span class="mro-circle optional" title="Optional"></span></td>
            <td><i class="fas fa-check text-success"></i></td>
            <td><i class="fas fa-check text-success"></i></td>
        </tr>
        <!-- taken -->
        <tr>
            <td>taken</td>
            <td><span class="mro-circle mandatory" title="Mandatory"></span></td>
            <td><i class="fas fa-check text-success"></i></td>
            <td><i class="fas fa-times text-danger"></i></td>
        </tr>
        <!-- reasonNotTaken -->
        <tr>
            <td>reasonNotTaken</td>
            <td><span class="mro-circle optional" title="Optional"></span></td>
            <td><i class="fas fa-check text-success"></i></td>
            <td><i class="fas fa-times text-danger"></i></td>
        </tr>
        <!-- reasonCode -->
        <tr>
            <td>reasonCode</td>
            <td><span class="mro-circle optional" title="Optional"></span></td>
            <td><i class="fas fa-check text-success"></i></td>
            <td><i class="fas fa-check text-success"></i></td>
        </tr>
        <!-- reasonReference -->
        <tr>
            <td>reasonReference</td>
            <td><span class="mro-circle optional" title="Optional"></span></td>
            <td><i class="fas fa-check text-success"></i></td>
            <td><i class="fas fa-check text-success"></i></td>
        </tr>
        <!-- note -->
        <tr>
            <td>note</td>
            <td><span class="mro-circle required" title="Required"></span></td>
            <td><i class="fas fa-check text-success"></i></td>
            <td><i class="fas fa-check text-success"></i></td>
        </tr>
        <!-- dosage -->
        <tr>
            <td>dosage</td>
            <td><span class="mro-circle mandatory" title="Mandatory"></span></td>
            <td><i class="fas fa-check text-success"></i></td>
            <td><i class="fas fa-check text-success"></i></td>
        </tr>
    </tbody>
</table>

---