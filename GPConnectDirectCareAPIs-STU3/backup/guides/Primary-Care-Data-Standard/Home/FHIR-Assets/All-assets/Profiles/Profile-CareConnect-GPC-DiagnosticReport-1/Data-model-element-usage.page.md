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
        <!-- basedOn -->
        <tr>
            <td>basedOn</td>
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
        <!-- code -->
        <tr>
            <td>code</td>
            <td><span class="mro-circle mandatory" title="Mandatory"></span></td>
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
        <!-- context -->
        <tr>
            <td>context</td>
            <td><span class="mro-circle optional" title="Optional"></span></td>
            <td><i class="fas fa-check text-success"></i></td>
            <td title="This element has been renamed to 'encounter' in FHIR R4"><i class="fas fa-exclamation text-warning"></i></td>
        </tr>
        <!-- effective[x] -->
        <tr>
            <td>effective[x]</td>
            <td><span class="mro-circle optional" title="Optional"></span></td>
            <td><i class="fas fa-check text-success"></i></td>
            <td><i class="fas fa-check text-success"></i></td>
        </tr>
        <!-- issued -->
        <tr>
            <td>issued</td>
            <td><span class="mro-circle mandatory" title="Mandatory"></span></td>
            <td><i class="fas fa-check text-success"></i></td>
            <td><i class="fas fa-check text-success"></i></td>
        </tr>
        <!-- performer -->
        <tr>
            <td>performer</td>
            <td><span class="mro-circle required" title="Required"></span></td>
            <td><i class="fas fa-check text-success"></i></td>
            <td><i class="fas fa-check text-success"></i></td>
        </tr>
        <!-- specimen -->
        <tr>
            <td>specimen</td>
            <td><span class="mro-circle required" title="Required"></span></td>
            <td><i class="fas fa-check text-success"></i></td>
            <td><i class="fas fa-check text-success"></i></td>
        </tr>
        <!-- result -->
        <tr>
            <td>result</td>
            <td><span class="mro-circle required" title="Required"></span></td>
            <td><i class="fas fa-check text-success"></i></td>
            <td><i class="fas fa-check text-success"></i></td>
        </tr>
        <!-- imagingStudy -->
        <tr>
            <td>imagingStudy</td>
            <td><span class="mro-circle optional" title="Optional"></span></td>
            <td><i class="fas fa-check text-success"></i></td>
            <td><i class="fas fa-check text-success"></i></td>
        </tr>
        <!-- image -->
        <tr>
            <td>image</td>
            <td><span class="mro-circle optional" title="Optional"></span></td>
            <td><i class="fas fa-check text-success"></i></td>
            <td><i class="fas fa-check text-success"></i></td>
        </tr>
        <!-- conclusion -->
        <tr>
            <td>conclusion</td>
            <td><span class="mro-circle required" title="Required"></span></td>
            <td><i class="fas fa-check text-success"></i></td>
            <td><i class="fas fa-check text-success"></i></td>
        </tr>
        <!-- codedDiagnosis -->
        <tr>
            <td>codedDiagnosis</td>
            <td><span class="mro-circle required" title="Required"></span></td>
            <td><i class="fas fa-check text-success"></i></td>
            <td title="This element has been renamed to 'conclusionCode' in FHIR R4"><i class="fas fa-exclamation text-warning"></i></td>
        </tr>
        <!-- presentedForm -->
        <tr>
            <td>presentedForm</td>
            <td><span class="mro-circle optional" title="Optional"></span></td>
            <td><i class="fas fa-check text-success"></i></td>
            <td><i class="fas fa-check text-success"></i></td>
        </tr>
    </tbody>
</table>


---