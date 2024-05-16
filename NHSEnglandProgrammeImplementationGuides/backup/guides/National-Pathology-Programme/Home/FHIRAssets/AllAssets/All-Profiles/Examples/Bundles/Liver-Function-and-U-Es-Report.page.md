---
topic: R4BundleExampleLFTandUandEReport
subject: Pathology-Bundle-LFT-UandE-Report-Example
---
### PATH-R4-12: Bundle Example - Liver Function Tests and Urea and Electrolytes Report

{{page:Home/FHIRAssets/AllAssets/All-Profiles/Examples/ExampleTabs.page.md}}
    
<div id="Example" role="tabpanel" class="tabcontent"  style="display:block"> 
   {{render:path-mockup-LFT-UandE-report}}
</div>
<div id="Notes" role="tabpanel" class="tabcontent">
    <br>
    <ul>
        <li>This is an example of a report that contains the results associated with multiple test groups.</li>
        <li>The test groups were requested as part of the same “event” (i.e. by the same practitioner at the same time for the same subject).</li>
        <li>An instance of <code>ServiceRequest</code> is required for each requested test group.</li>
        <li>Each <code>ServiceRequest</code> within a set of related requests uses a common identifier, <code>ServiceRequest.requisition</code>, to link them together. For further information, refer to the description of the {{pagelink:R4ServiceRequest}} profile.</li>
        <li>In this example, the specimen (venous blood) was collected after the request was made. The specimen is linked to the request within the <code>Bundle</code> using <code>Specimen.request</code>.</li>	
    </ul>
</div>
<div id="DataModel" role="tabpanel" class="tabcontent">
<br>
<p>The following is a simplified logical data model that illustrates the key references between the FHIR profiles in the example message bundle. To aid clarity, not all of the references are shown. For a detailed description of the relationships between the FHIR profiles, and how they may be used, refer to {{pagelink:BuildContructPathologyReportBundle}}.</p>
<br>
{{render:path-data-model-LFT-UandE-report}}
</div>

{{page:Home/FHIRAssets/AllAssets/All-Profiles/Examples/ExampleRenders.page.md}}