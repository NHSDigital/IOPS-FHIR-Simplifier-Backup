### Pathology Business Information Model and FHIR Profile Mapping
The following diagram is a high-level logical representation of the key business entities relating to pathology test requesting and reporting:

{{render:path-diagram-information-model}}

To aid clarity, individual and organisation type entities (e.g. Performer / Performing Organisation) have been combined in the diagram but may be referenced independently. Each business entity is summarised below, together with links to the corresponding FHIR R4 resource (as defined in the base [FHIR R4 specification](https://hl7.org/fhir/R4/)) and FHIR UK Core R4 profile (as described in the {{pagelink:FHIRAssetsR4Profiles}} section of this implementation guide).

<table class="regular">
    <thead>
        <tr>
            <th width="20%">Business Entity Name</th>
            <th width="45%">Description</th>
            <th width="15%">FHIR R4 Resource</th>
            <th width="25%">FHIR UK Core R4 Profile</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Test Request Summary</td>
            <td>A summary of the original test request that is returned with the <b>Test Report</b>.</td>
            <td><a href="https://hl7.org/fhir/R4/servicerequest.html">ServiceRequest</a></td>
            <td>{{pagelink:R4ServiceRequest}}</td>         
        </tr>
        <tr>
            <td>Specimen</td>
            <td>Details relating to the specimen(s) provided for testing.</td>
            <td><a href="https://hl7.org/fhir/R4/specimen.html">Specimen</a></td>
            <td>{{pagelink:R4Specimen}}</td>
        </tr>
        <tr>
            <td>Test Report</td>
            <td>The overall findings and clinical interpretation relating to one or more pathology tests or investigations. The report may reference individual <b>Test Results</b>, <b>Test Groups</b> or a combination of these.</td>
            <td><a href="https://hl7.org/fhir/R4/diagnosticreport.html">DiagnosticReport</a></td>
            <td>{{pagelink:R4DiagnosticReport}}</td>
        </tr>
        <tr>
            <td>Test Group</td>
            <td>A set of related tests, for example a Full Blood Count. <b>Test Groups</b> are often referred to as batteries, panels or profiles. Multiple levels of <b>Test Groups</b> and <b>Test Results</b> may be nested to support complex report structures, such as those used in Microscopy, Culture and Sensitivity reports.</td>
            <td><a href="https://hl7.org/fhir/R4/observation.html">Observation</a></td>
            <td>{{pagelink:R4ObservationTestGroup}}</td>
        </tr>
        <tr>
            <td>Test Result</td>
            <td>A single test result. Includes the name and associated SNOMED CT code for the test (e.g. “Glucose substance concentration in plasma” – 1110521000000108) and the result, with an accompanying unit of measure where appropriate (e.g. 4.8 mmol/L).</td>
            <td><a href="https://hl7.org/fhir/R4/observation.html">Observation</a></td>
            <td>{{pagelink:R4ObservationTestResult}}</td>
        </tr>
        <tr>
            <td>Patient</td>
            <td>Demographics and other administrative information relating to a patient.</td>
            <td><a href="https://hl7.org/fhir/R4/patient.html">Patient</a></td>
            <td>{{pagelink:R4Patient}}</td>
        </tr>
        <tr>
            <td rowspan="2">Requester</td>
            <td rowspan="2">Details relating to the individual that requested a pathology test.</td>
            <td><a href="https://hl7.org/fhir/R4/practitioner.html">Practitioner</a></td>
            <td>{{pagelink:R4Practitioner}}</td>
        </tr>
        <tr>
            <td><a href="https://hl7.org/fhir/R4/practitionerrole.html">PractitionerRole</a></td>
            <td>{{pagelink:R4PractitionerRole}}</td>
        </tr>
        <tr>
            <td>Requesting Organisation </td>
            <td>Details relating to the organisation that requested a pathology test.</td>
            <td><a href="https://hl7.org/fhir/R4/organization.html">Organization</a></td>
            <td>{{pagelink:R4Organization}}</td>
        </tr>
        <tr>
            <td rowspan="2">Specimen Collector</td>
            <td rowspan="2">Details relating to the individual that collected a specimen.</td>
            <td><a href="https://hl7.org/fhir/R4/practitioner.html">Practitioner</a></td>
            <td>{{pagelink:R4Practitioner}}</td>
        </tr>
        <tr>
            <td><a href="https://hl7.org/fhir/R4/practitionerrole.html">PractitionerRole</a></td>
            <td>{{pagelink:R4PractitionerRole}}</td>
        </tr>
        <tr>
            <td>Specimen Collecting Organisation</td>
            <td>Details relating to the organisation that collected a specimen.</td>
            <td><a href="https://hl7.org/fhir/R4/organization.html">Organization</a></td>
            <td>{{pagelink:R4Organization}}</td>
        </tr>
        <tr>
            <td rowspan="2">Performer</td>
            <td rowspan="2">Details relating to the individual that performed a pathology test.</td>
            <td><a href="https://hl7.org/fhir/R4/practitioner.html">Practitioner</a></td>
            <td>{{pagelink:R4Practitioner}}</td>
        </tr>
        <tr>
            <td><a href="https://hl7.org/fhir/R4/practitionerrole.html">PractitionerRole</a></td>
            <td>{{pagelink:R4PractitionerRole}}</td>
        </tr>
        <tr>
            <td>Performing Organisation</td>
            <td>Details relating to the organisation that performed a pathology test.</td>
            <td><a href="https://hl7.org/fhir/R4/organization.html">Organization</a></td>
            <td>{{pagelink:R4Organization}}</td>
        </tr>
    </tbody>
</table>