---
topic: R4BundleExampleCRPReport
subject: Pathology-Bundle-CRP-Report-Example
---
### PATH-R4-04: Bundle Example - C-Reactive Protein Report

{{page:Home/FHIRAssets/AllAssets/All-Profiles/Examples/ExampleTabs.page.md}}
    
<div id="Example" role="tabpanel" class="tabcontent"  style="display:block"> 
    {{render:path-mockup-CRP-report}}
</div>
<div id="Notes" role="tabpanel" class="tabcontent">
    <br>
    <ul>
        <li>This is an example of a report that contains a single test result.</li>
        <li>The test result is defined as an <code>Observation</code> and is referenced from <code>DiagnosticReport</code> using <code>DiagnosticReport.result</code>.</li>
        <li>The test result type is numeric and is specified using <code>Observation.valueQuantity</code>.</li>
        <li>The test result value is high (200 mg/L, compared to the standard reference range of 0-5 mg/L). This is indicated by populating <code>Observation.interpretation</code> with a code value of <code>H</code/> for <code>High</code>.</li>
    </ul>
</div>
<div id="DataModel" role="tabpanel" class="tabcontent">
    <br>
    <p>The following is a simplified logical data model that illustrates the key references between the FHIR profiles in the example message bundle. To aid clarity, not all of the references are shown. For a detailed description of the relationships between the FHIR profiles, and how they may be used, refer to {{pagelink:BuildContructPathologyReportBundle}}.</p>
    <br>
    {{render:path-data-model-CRP-report}}
</div>
{{page:Home/FHIRAssets/AllAssets/All-Profiles/Examples/ExampleRenders.page.md}}