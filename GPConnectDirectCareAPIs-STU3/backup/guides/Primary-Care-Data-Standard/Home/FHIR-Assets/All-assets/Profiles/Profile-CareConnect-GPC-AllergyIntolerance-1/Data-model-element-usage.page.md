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
        <!-- extension(encounter) -->
        <tr>
            <td>extension(encounter)</td>
            <td><span class="mro-circle required" title="Required"></span></td>
            <td><i class="fas fa-check text-success"></i></td>
            <td><i class="fas fa-exclamation text-warning" title="The UK Core resource has an encounter element in the base resource"></i></td>
        </tr>
        <!-- extension(allergyEnd) -->
        <tr>
            <td>extension(allergyEnd)</td>
            <td><span class="mro-circle required" title="Required"></span></td>
            <td><i class="fas fa-exclamation text-warning" title="This element is named 'endDate' in CareConnect"></i></td>
            <td><i class="fas fa-check text-success"></i></td>
        </tr>
        <!-- extension(evidence) -->
        <tr>
            <td>extension(evidence)</td>
            <td><span class="mro-circle optional" title="Optional"></span></td>
            <td><i class="fas fa-check text-success"></i></td>
            <td><i class="fas fa-check text-success"></i></td>
        </tr>
        <!-- identifier -->
        <tr>
            <td>identifier</td>
            <td><span class="mro-circle mandatory" title="Mandatory"></span></td>
            <td><i class="fas fa-check text-success"></i></td>
            <td><i class="fas fa-check text-success"></i></td>
        </tr>
        <!-- clinicalStatus -->
        <tr>
            <td>clinicalStatus</td>
            <td><span class="mro-circle mandatory" title="Mandatory"></span></td>
            <td><i class="fas fa-check text-success"></i></td>
            <td><i class="fas fa-check text-success"></i></td>
        </tr>
        <!-- verificationStatus -->
        <tr>
            <td>verificationStatus</td>
            <td><span class="mro-circle mandatory" title="Mandatory"></span></td>
            <td><i class="fas fa-check text-success"></i></td>
            <td><i class="fas fa-check text-success"></i></td>
        </tr>
        <!-- type -->
        <tr>
            <td>type</td>
            <td><span class="mro-circle optional" title="Optional"></span></td>
            <td><i class="fas fa-check text-success"></i></td>
            <td><i class="fas fa-check text-success"></i></td>
        </tr>
        <!-- category -->
        <tr>
            <td>category</td>
            <td><span class="mro-circle mandatory" title="Mandatory"></span></td>
            <td><i class="fas fa-check text-success"></i></td>
            <td><i class="fas fa-check text-success"></i></td>
        </tr>
        <!-- criticality -->
        <tr>
            <td>criticality</td>
            <td><span class="mro-circle required" title="Required"></span></td>
            <td><i class="fas fa-check text-success"></i></td>
            <td><i class="fas fa-check text-success"></i></td>
        </tr>
        <!-- code -->
        <tr>
            <td>code</td>
            <td><span class="mro-circle mandatory" title="Mandatory"></span></td>
            <td><i class="fas fa-check text-success"></i></td>
            <td><i class="fas fa-check text-success"></i></td>
        </tr>
        <!-- patient -->
        <tr>
            <td>patient</td>
            <td><span class="mro-circle mandatory" title="Mandatory"></span></td>
            <td><i class="fas fa-check text-success"></i></td>
            <td><i class="fas fa-check text-success"></i></td>
        </tr>
        <!-- onset.onsetDateTune -->
        <tr>
            <td>onset.onsetDateTime</td>
            <td><span class="mro-circle required" title="Required"></span></td>
            <td><i class="fas fa-check text-success"></i></td>
            <td><i class="fas fa-check text-success"></i></td>
        </tr>
        <!-- assertedDate -->
        <tr>
            <td>assertedDate</td>
            <td><span class="mro-circle mandatory" title="Mandatory"></span></td>
            <td><i class="fas fa-check text-success"></i></td>
            <td><i class="fas fa-check text-success"></i></td>
        </tr>
        <!-- recorder -->
        <tr>
            <td>recorder</td>
            <td><span class="mro-circle mandatory" title="Mandatory"></span></td>
            <td><i class="fas fa-check text-success"></i></td>
            <td><i class="fas fa-check text-success"></i></td>
        </tr>
        <!-- asserter -->
        <tr>
            <td>asserter</td>
            <td><span class="mro-circle required" title="Required"></span></td>
            <td><i class="fas fa-check text-success"></i></td>
            <td><i class="fas fa-check text-success"></i></td>
        </tr>
        <!-- lastOccurrence -->
        <tr>
            <td>lastOccurrence</td>
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
        <!-- reaction.substance -->
        <tr>
            <td>reaction.substance</td>
            <td><span class="mro-circle optional" title="Optional"></span></td>
            <td><i class="fas fa-check text-success"></i></td>
            <td><i class="fas fa-check text-success"></i></td>
        </tr>
        <!-- reaction.manifestation -->
        <tr>
            <td>reaction.manifestation</td>
            <td><span class="mro-circle optional" title="Optional"></span></td>
            <td><i class="fas fa-check text-success"></i></td>
            <td><i class="fas fa-check text-success"></i></td>
        </tr>
        <!-- reaction.description -->
        <tr>
            <td>reaction.description</td>
            <td><span class="mro-circle optional" title="Optional"></span></td>
            <td><i class="fas fa-check text-success"></i></td>
            <td><i class="fas fa-check text-success"></i></td>
        </tr>
        <!-- reaction.onset[x] -->
        <tr>
            <td>reaction.onset[x]</td>
            <td><span class="mro-circle optional" title="Optional"></span></td>
            <td><i class="fas fa-check text-success"></i></td>
            <td><i class="fas fa-check text-success"></i></td>
        </tr>
        <!-- reaction.severity -->
        <tr>
            <td>reaction.severity</td>
            <td><span class="mro-circle required" title="Required"></span></td>
            <td><i class="fas fa-check text-success"></i></td>
            <td><i class="fas fa-check text-success"></i></td>
        </tr>
        <!-- reaction.exposureRoute -->
        <tr>
            <td>reaction.exposureRoute</td>
            <td><span class="mro-circle optional" title="Optional"></span></td>
            <td><i class="fas fa-check text-success"></i></td>
            <td><i class="fas fa-check text-success"></i></td>
        </tr>
        <!-- reaciton.note -->
        <tr>
            <td>reaction.note</td>
            <td><span class="mro-circle optional" title="Optional"></span></td>
            <td><i class="fas fa-check text-success"></i></td>
            <td><i class="fas fa-check text-success"></i></td>
        </tr>
    </tbody>
</table>

---