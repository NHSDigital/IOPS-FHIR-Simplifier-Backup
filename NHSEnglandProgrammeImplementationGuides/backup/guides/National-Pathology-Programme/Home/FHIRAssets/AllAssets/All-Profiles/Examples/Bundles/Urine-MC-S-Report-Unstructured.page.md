---
topic: R4BundleExampleUrineMCSReportUnstructured
subject: Pathology-Bundle-Urine-MCS-01-Unstructured-Report-Example
---
### PATH-R4-18a: Bundle Example - Urine Microscopy, Culture and Sensitivity Report (Unstructured)
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
{{render:path-mockup-MCS-01-report}}
</div>
<div id="Notes" role="tabpanel" class="tabcontent">
    <br>
    <ul>
        <li>This is an example of a complex report.</li>
        <li>The results are represented using a single <code>Observation</code> and formatted as a blob of text.</li>
        <li>The report includes a range of numeric, semi-quantitative and qualitative results.</li>
        <li>In this example, the specimen (urine) was collected after the request was made. The specimen is linked to the request within the <code>Bundle</code> using <code>Specimen.request</code>.</li>
    </ul>
</div>
<div id="DataModel" role="tabpanel" class="tabcontent">
    <br>
    <p>The following is a simplified logical data model that illustrates the key references between the FHIR profiles in the example message bundle. To aid clarity, not all of the references are shown. For a detailed description of the relationships between the FHIR profiles, and how they may be used, refer to {{pagelink:BuildContructPathologyReportBundle}}.</p>
    <br>
    {{render:path-data-model-MCS-01-unstructured-report}}
</div>
{{page:Home/FHIRAssets/AllAssets/All-Profiles/Templates/ExampleRendersTemplate.page.md}}