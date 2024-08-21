---
topic: R4BundleExampleGTTReportUnstructured
subject: Pathology-Bundle-GTT-Unstructured-Report-Example
---
### PATH-R4-16a: Bundle Example - Glucose Tolerance Test  Report (Unstructured)
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
   {{render:path-mockup-GTT-report}}
</div>
<div id="Notes" role="tabpanel" class="tabcontent">
    <br>
    <ul>
        <li>This is an example of a Glucose Tolerance Test (GTT) report, which is a type of dynamic function test.</li>
        <li>Dynamic function tests measure the outcome of certain stimulants (or suppressants) usually invoked on the endocrine system. A series of specimens is collected at defined time intervals and the results are reported together as a chronological sequence.</li>
        <li>Each specimen is represented as a separate <code>Specimen</code> instance.</li>
        <li>In this example, the patient fasted before the first specimen was taken. This is indicated using <code>Specimen.collection.fastingStatus[x]</code>.</li>
        <li>The results are represented using a single <code>Observation</code> and formatted as a blob of text.</li>
        <li>A clinical interpretation/summary of the test results is carried in <code>DiagnosticReport.conclusion</code>.</li>
    </ul>
</div>
<div id="DataModel" role="tabpanel" class="tabcontent">
    <br>
    <p>The following is a simplified logical data model that illustrates the key references between the FHIR profiles in the example message bundle. To aid clarity, not all of the references are shown. For a detailed description of the relationships between the FHIR profiles, and how they may be used, refer to {{pagelink:BuildContructPathologyReportBundle}}.</p>
    <br>
    {{render:path-data-model-GTT-unstructured-report}}
</div>
{{page:Home/FHIRAssets/AllAssets/All-Profiles/Templates/ExampleRendersTemplate.page.md}}