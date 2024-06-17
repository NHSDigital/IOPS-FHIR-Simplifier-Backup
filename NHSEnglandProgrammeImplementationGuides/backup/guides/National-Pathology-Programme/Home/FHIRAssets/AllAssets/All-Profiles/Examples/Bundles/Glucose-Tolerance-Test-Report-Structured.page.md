---
topic: R4BundleExampleGTTReportStructured
subject: Pathology-Bundle-GTT-Report-Example
---
### PATH-R4-16b: Bundle Example - Glucose Tolerance Test Report (Structured)

{{page:Home/FHIRAssets/AllAssets/All-Profiles/Examples/ExampleTabs.page.md}}
    
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
        <li>The results are represented using a set of structured, coded <code>Observations</code>. These are grouped using a parent level test group <code>Observation</code>.</li>
        <li>The core <a href="https://hl7.org/fhir/R4/extension-observation-sequelto.html">observation-sequelTo</a> extension is used to link the test result <code>Observations</code> to one another in a chronological sequence.</li>
        <li>The relative time interval associated with each test result <code>Observation</code> (e.g. 30 minutes) is carried using <code>Observation.component</code>.</li>           </ul>
</div>
<div id="DataModel" role="tabpanel" class="tabcontent">
    <br>
    <p>The following is a simplified logical data model that illustrates the key references between the FHIR profiles in the example message bundle. To aid clarity, not all of the references are shown. For a detailed description of the relationships between the FHIR profiles, and how they may be used, refer to {{pagelink:BuildContructPathologyReportBundle}}.</p>
    <br>
    {{render:path-data-model-GTT-report}}
</div>

{{page:Home/FHIRAssets/AllAssets/All-Profiles/Examples/ExampleRenders.page.md}}