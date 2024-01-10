## {{page-title}}

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
  <strong>Important</strong>: This profile does exists in UK Core as <a href="https://simplifier.net/hl7fhirukcorer4/ukcore-condition">UKCore-Condition</a>.
</div>

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
        <!-- extension(actualProblem) -->
        <tr>
            <td>extension(actualProblem)</td>
            <td><span class="mro-circle required" title="Required"></span></td>
            <td><i class="fas fa-check text-success"></i></td>
            <td><i class="fas fa-check text-success"></i></td>
        </tr>
        <!-- extension(relatedProblem) -->
        <tr>
            <td>extension(relatedProblem)</td>
            <td><span class="mro-circle required" title="Required"></span></td>
            <td><i class="fas fa-exclamation text-warning" title="Exists as 'relatedProblemHeader' in CareConnect"></i></td>
            <td><i class="fas fa-exclamation text-warning" title="Exists as 'relatedProblemHeader' in UK Core"></i></td>
        </tr>
        <!-- extension(problemSignificance) -->
        <tr>
            <td>extension(problemSignificance)</td>
            <td><span class="mro-circle required" title="Required"></span></td>
            <td><i class="fas fa-check text-success"></i></td>
            <td><i class="fas fa-check text-success"></i></td>
        </tr>
        <!-- extension(relatedClinicalContent) -->
        <tr>
            <td>extension(relatedClinicalContent)</td>
            <td><span class="mro-circle required" title="Required"></span></td>
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
        <!-- severity -->
        <tr>
            <td>severity</td>
            <td><span class="mro-circle optional" title="Optional"></span></td>
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
        <!-- bodySite -->
        <tr>
            <td>bodySite</td>
            <td><span class="mro-circle optional" title="Optional"></span></td>
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
            <td><span class="mro-circle required" title="Required"></span></td>
            <td><i class="fas fa-check text-success"></i></td>
            <td><i class="fas fa-check text-success"></i></td>
        </tr>
        <!-- onset -->
        <tr>
            <td>onset</td>
            <td><span class="mro-circle required" title="Required"></span></td>
            <td><i class="fas fa-check text-success"></i></td>
            <td><i class="fas fa-check text-success"></i></td>
        </tr>
        <!-- abatement -->
        <tr>
            <td>abatement</td>
            <td><span class="mro-circle required" title="Required"></span></td>
            <td><i class="fas fa-check text-success"></i></td>
            <td><i class="fas fa-check text-success"></i></td>
        </tr>
        <!-- assertedDate -->
        <tr>
            <td>onset</td>
            <td><span class="mro-circle mandatory" title="Mandatory"></span></td>
            <td><i class="fas fa-check text-success"></i></td>
            <td><i class="fas fa-check text-success"></i></td>
        </tr>
        <!-- asserter -->
        <tr>
            <td>asserter</td>
            <td><span class="mro-circle mandatory" title="Mandatory"></span></td>
            <td><i class="fas fa-check text-success"></i></td>
            <td><i class="fas fa-check text-success"></i></td>
        </tr>
        <!-- stage -->
        <tr>
            <td>stage</td>
            <td><span class="mro-circle optional" title="Optional"></span></td>
            <td><i class="fas fa-check text-success"></i></td>
            <td><i class="fas fa-check text-success"></i></td>
        </tr>
        <!-- evidence -->
        <tr>
            <td>evidence</td>
            <td><span class="mro-circle optional" title="Optional"></span></td>
            <td><i class="fas fa-check text-success"></i></td>
            <td><i class="fas fa-check text-success"></i></td>
        </tr>
        <!-- note -->
        <tr>
            <td>note</td>
            <td><span class="mro-circle optional" title="Optional"></span></td>
            <td><i class="fas fa-check text-success"></i></td>
            <td><i class="fas fa-check text-success"></i></td>
        </tr>
    </tbody>
</table>

---