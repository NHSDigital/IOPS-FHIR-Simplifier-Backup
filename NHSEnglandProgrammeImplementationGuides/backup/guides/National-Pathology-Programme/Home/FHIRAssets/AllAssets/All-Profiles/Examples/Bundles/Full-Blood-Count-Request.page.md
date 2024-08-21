---
topic: R4BundleExampleFullBloodCountRequest
subject: Pathology-Bundle-FBC-Request-Example
---
### PATH-R4-09: Bundle Example - Full Blood Count Request
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
    {{render:path-mockup-FBC-request}}
</div>
<div id="Notes" role="tabpanel" class="tabcontent">
    <br>
    <ul>
        <li>This is an example of a request for a single test group.</li>		    <li>Within the context of this specification a test group is defined as a set of related tests. Test groups are often referred to as batteries, panels or profiles.</li>
        <li><code>ServiceRequest.code</code> is used to specify the requested test group.</li>
        <li>An explanation that describes why the tests have been requested is carried in <code>ServiceRequest.reasonCode</code>. In this example, clinical information is provided as free text (“Tired all the time, shortness of breath, arrhythmia") and so the <code>CodeableConcept.text</code> element is used.</li>
    </ul>
</div>
<div id="DataModel" role="tabpanel" class="tabcontent">
    <br>
    <p>The following is a simplified logical data model that illustrates the key references between the FHIR profiles in the example message bundle. To aid clarity, not all of the references are shown. For a detailed description of the relationships between the FHIR profiles, and how they may be used, refer to {{pagelink:BuildContructPathologyRequestBundle}}.</p>
    <br>
    {{render:path-data-model-FBC-request}}
</div>
{{page:Home/FHIRAssets/AllAssets/All-Profiles/Templates/ExampleRendersTemplate.page.md}}