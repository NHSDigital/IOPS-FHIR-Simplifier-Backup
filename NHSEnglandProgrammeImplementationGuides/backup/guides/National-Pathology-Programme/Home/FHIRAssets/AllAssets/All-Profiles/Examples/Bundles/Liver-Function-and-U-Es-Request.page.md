---
topic: R4BundleExampleLFTandUandERequest
subject: Pathology-Bundle-LFT-UandE-Request-Example
---
### PATH-R4-13: Bundle Example - Liver Function Tests and Urea and Electrolytes Request
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
   {{render:path-mockup-LFT-UandE-request}}
</div>
<div id="Notes" role="tabpanel" class="tabcontent">
    <br>
    <ul>
        <li>This is an example of a request for multiple test groups.</li>
        <li>In this example, multiple test groups are being requested as part of the same “event” (i.e. by the same practitioner at the same time for the same subject).</li>
        <li>An instance of <code>ServiceRequest</code> is required for each requested test group. <b>Note: </b> <code>ServiceRequest.code</code>, which is used to specify the requested test, has a cardinality of 0..1.</li>
        <li>Each <code>ServiceRequest</code> within a set of related requests uses a common identifier, <code>ServiceRequest.requisition</code>, to link them together. For further information, refer to the description of the {{pagelink:R4ServiceRequest}} profile.</li>
    </ul>
</div>
<div id="DataModel" role="tabpanel" class="tabcontent">
    <br>
    <p>The following is a simplified logical data model that illustrates the key references between the FHIR profiles in the example message bundle. To aid clarity, not all of the references are shown. For a detailed description of the relationships between the FHIR profiles, and how they may be used, refer to {{pagelink:BuildContructPathologyRequestBundle}}.</p>
    <br>
    {{render:path-data-model-LFT-UandE-request}}
</div>
{{page:Home/FHIRAssets/AllAssets/All-Profiles/Templates/ExampleRendersTemplate.page.md}}
