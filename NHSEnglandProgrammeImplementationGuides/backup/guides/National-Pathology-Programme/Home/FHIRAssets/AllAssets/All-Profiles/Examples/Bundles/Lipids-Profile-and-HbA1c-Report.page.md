---
topic: R4BundleExampleLipidsandHbA1cReport
subject: Pathology-Bundle-Lipids-HbA1c-Report-Example
---
### PATH-R4-12: Bundle Example - Lipids Profile and Haemoglobin A1c (HbA1c) Report

{{page:Home/FHIRAssets/AllAssets/All-Profiles/Examples/ExampleTabs.page.md}}
    
<div id="Example" role="tabpanel" class="tabcontent"  style="display:block"> 
   {{render:path-mockup-lipids-HbA1c-report}}
</div>
<div id="Notes" role="tabpanel" class="tabcontent">
    <br>
    <ul>
        <li>This is an example of a report that contains the results associated with a single test group and a single test.</li>
        <li>The tests were requested as part of the same “event” (i.e. by the same practitioner at the same time for the same subject).</li>
        <li>An instance of <code>ServiceRequest</code> is required for the test group and a separate instance of <code>ServiceRequest</code> is required for the single test.</li>
        <li>Each <code>ServiceRequest</code> within a set of related requests uses a common identifier, <code>ServiceRequest.requisition</code>, to link them together. For further information, refer to the description of the {{pagelink:R4ServiceRequest}} profile.</li>
        <li>In this example, the specimen (venous blood) was collected after the request was made. The specimen is linked to the request within the <code>Bundle</code> using <code>Specimen.request</code>.</li>	
    </ul>
</div>
<div id="DataModel" role="tabpanel" class="tabcontent">
    <br>
    <p>The following is a simplified logical data model that illustrates the key references between the FHIR profiles in the example message bundle. To aid clarity, not all of the references are shown. For a detailed description of the relationships between the FHIR profiles, and how they may be used, refer to {{pagelink:BuildContructPathologyReportBundle}}.</p>
    <br>
    {{render:path-data-model-lipids-HbA1c-report}}
</div>

{{page:Home/FHIRAssets/AllAssets/All-Profiles/Examples/ExampleRenders.page.md}}