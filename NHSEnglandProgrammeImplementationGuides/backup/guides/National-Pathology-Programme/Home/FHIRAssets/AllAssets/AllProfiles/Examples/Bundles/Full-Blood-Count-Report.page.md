---
topic: R4BundleExampleFullBloodCountReport
subject: Pathology-Bundle-FBC-Report-Example
---
### PATH-R4-10: Bundle Example - Full Blood Count Report
<div class="tab fhirTree">
    <button class="tablinks active" onclick="openTab(event, 'Example')">Example</button>
    <button class="tablinks" onclick="openTab(event, 'Notes')">Notes</button>
    <button class="tablinks" onclick="openTab(event, 'DataModel')">Data Model</button>
    <button class="tablinks" onclick="openTab(event, 'XML')">XML</button>
    <button class="tablinks" onclick="openTab(event, 'JSON')">JSON</button>
    <button class="tablinks" onclick="openTab(event, 'Tree')">Tree</button>
    <button class="tablinks" onclick="openTab(event, 'Table')">Table</button>
</div>
<div id="Example" role="tabpanel" class="tabcontent"  style="display:block"> 
    {{render:path-mockup-FBC-report}}
</div>
<div id="Notes" role="tabpanel" class="tabcontent">
    <br>
	<ul>
        <li>This is an example of a report that contains the results associated with a single test group.</li>
        <li>Within the context of this specification a test group is defined as a set of related tests. Test groups are often referred to as batteries, panels or profiles.</li>
        <li>The test group is defined as an <code>Observation</code> and is referenced from <code>DiagnosticReport</code> using <code>DiagnosticReport.result</code>. The test group <code>Observation</code> references other <code>Observations</code> that contain the associated test results. The references are defined using <code>Observation.hasMember</code>.</li>
        <li>In this example, the specimen (venous blood) was collected after the request was made. The specimen is linked to the request within the <code>Bundle</code> using <code>Specimen.request</code>.</li>
        <li>An explanation that describes why the tests have been requested is carried in <code>ServiceRequest.reasonCode</code>. In this example, clinical information is provided as free text (“Tired all the time, shortness of breath, arrhythmia") and so the <code>CodeableConcept.text</code> element is used.</li>  
    </ul>
</div>
<div id="DataModel" role="tabpanel" class="tabcontent">
    <br>
    <p>The following is a simplified logical data model that illustrates the key references between the FHIR profiles in the example message bundle. To aid clarity, not all of the references are shown. For a detailed description of the relationships between the FHIR profiles, and how they may be used, refer to {{pagelink:BuildContructPathologyReportBundle}}.</p>
    <br>
    {{render:path-data-model-FBC-report}}
</div>
{{page:Home/FHIRAssets/AllAssets/AllProfiles/Templates/ExampleRendersTemplate.page.md}}