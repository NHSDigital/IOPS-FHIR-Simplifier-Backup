---
topic: R4BundleExampleCRPRequest
subject: Pathology-Bundle-CRP-Request-Example
---
### PATH-R4-03: Bundle Example - C-Reactive Protein Request

{{page:Home/FHIRAssets/AllAssets/All-Profiles/Examples/ExampleTabs.page.md}}
    
<div id="Example" role="tabpanel" class="tabcontent"  style="display:block"> 
    {{render:path-mockup-CRP-request}}
</div>
<div id="Notes" role="tabpanel" class="tabcontent">
    <br>
    <ul>
        <li>This is an example of a request for a single test.</li>
        <li><code>ServiceRequest.code</code> is used to specify the requested test.</li>				
        <li>In this example, the specimen (venous blood) was collected at the point that the request was made. The request is linked to the specimen within the <code>Bundle</code> using <code>ServiceRequest.specimen</code>.</li>
    </ul>
</div>
<div id="DataModel" role="tabpanel" class="tabcontent">
<br>
<p>The following is a simplified logical data model that illustrates the key references between the FHIR profiles in the example message bundle. To aid clarity, not all of the references are shown. For a detailed description of the relationships between the FHIR profiles, and how they may be used, refer to {{pagelink:BuildContructPathologyRequestBundle}}.</p>
<br>
{{render:path-data-model-CRP-request}}
</div>

{{page:Home/FHIRAssets/AllAssets/All-Profiles/Examples/ExampleRenders.page.md}}