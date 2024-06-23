---
topic: R4BundleExampleHbA1cReport
subject: Pathology-Bundle-HbA1c-Report-Example
---
### PATH-R4-02: Bundle Example - Haemoglobin A1c (HbA1c) Report

{{page:Home/FHIRAssets/AllAssets/All-Profiles/Examples/ExampleTabs.page.md}}
    
<div id="Example" role="tabpanel" class="tabcontent"  style="display:block"> 
    {{render:path-mockup-HbA1c-report}}
</div>
<div id="Notes" role="tabpanel" class="tabcontent">
    <br>
    <ul>
        <li>This is an example of a report that contains a single test result.</li>
        <li>The test result is defined as an <code>Observation</code> and is referenced from <code>DiagnosticReport</code> using <code>DiagnosticReport.result</code>.</li>
        <li>The test result type is numeric and is specified using <code>Observation.valueQuantity</code>.</li>
        <li>Detailed narrative-based reference range information for the test result is carried in <code>Observation.referenceRange.text</code>.</li>
    </ul>
</div>
<div id="DataModel" role="tabpanel" class="tabcontent">
    <br>
    <p>The following is a simplified logical data model that illustrates the key references between the FHIR profiles in the example message bundle. To aid clarity, not all of the references are shown. For a detailed description of the relationships between the FHIR profiles, and how they may be used, refer to {{pagelink:BuildContructPathologyReportBundle}}.</p>
    <br>
    {{render:path-data-model-HbA1c-report}}
</div>
{{page:Home/FHIRAssets/AllAssets/All-Profiles/Examples/ExampleRenders.page.md}}