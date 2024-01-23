---
topic: R4BundleExampleFullBloodCountRequest
---
### PATH-R4-03: R4 Bundle Example - Full Blood Count Request

<div class="tab fhirTree">
    <button class="tablinks active" onclick="openTab(event, 'Example')">Example Request</button>
    <button class="tablinks" onclick="openTab(event, 'Notes')">Notes</button>
    <button class="tablinks" onclick="openTab(event, 'DataModel')">Data Model</button>
    <button class="tablinks" onclick="openTab(event, 'XML')">XML</button>
    <button class="tablinks" onclick="openTab(event, 'JSON')">JSON</button>
    <button class="tablinks" onclick="openTab(event, 'Tree')">Tree</button>
</div>
    
<div id="Example" role="tabpanel" class="tabcontent"  style="display:block"> 
    {{render:path-mockup-FBC-request}}
</div>
<div id="Notes" role="tabpanel" class="tabcontent">
    <br>
    <ul>
        <li>This is an example of a request for a single test group.</li>		    <li>Within the context of this specification a test group is defined as a set of related tests. Test groups are often referred to as batteries, panels or profiles.</li>
        <li><code>ServiceRequest.code</code> is used to specify the requested test group.</li>
    </ul>
</div>
<div id="DataModel" role="tabpanel" class="tabcontent">
    <br>
    <p>The following is a simplified logical data model that illustrates the key references between the FHIR profiles in the example message bundle. To aid clarity, not all of the references are shown. For a detailed description of the relationships between the FHIR profiles, and how they may be used, refer to {{pagelink:BuildContructPathologyRequestBundle}}.</p>
    <br>
    {{render:path-data-model-FBC-request}}
</div>
<div id="XML" role="tabpanel" class="tabcontent">
    {{xml:Pathology-Bundle-FBC-Request-Example}}
</div>
<div id="JSON" role="tabpanel" class="tabcontent">
    {{json:Pathology-Bundle-FBC-Request-Example}}
</div>
<div id="Tree" role="tabpanel" class="tabcontent expandedexample">
    {{tree:Pathology-Bundle-FBC-Request-Example}}
</div>