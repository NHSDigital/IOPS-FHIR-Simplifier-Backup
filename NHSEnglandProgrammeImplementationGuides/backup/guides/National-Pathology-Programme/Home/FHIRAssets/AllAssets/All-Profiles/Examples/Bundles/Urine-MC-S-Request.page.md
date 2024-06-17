---
topic: R4BundleExampleUrineMCSRequest
subject: Pathology-Bundle-Urine-MCS-01-Request-Example
---
### PATH-R4-17: Bundle Example - Urine Microscopy, Culture and Sensitivity Request


{{page:Home/FHIRAssets/AllAssets/All-Profiles/Examples/ExampleTabs.page.md}}
    
<div id="Example" role="tabpanel" class="tabcontent"  style="display:block"> 
  {{render:path-mockup-MCS-01-request}}
</div>
<div id="Notes" role="tabpanel" class="tabcontent">
<br>
<ul>
    <li>This is an example of a request for a single, complex test.</li>
    <li><code>ServiceRequest.code</code> is used to specify the requested test.</li>
    <li>The associated test report contains multiple levels of test groups and test results.</li>
</ul>
</div>
<div id="DataModel" role="tabpanel" class="tabcontent">
<br>
<p>The following is a simplified logical data model that illustrates the key references between the FHIR profiles in the example message bundle. To aid clarity, not all of the references are shown. For a detailed description of the relationships between the FHIR profiles, and how they may be used, refer to {{pagelink:BuildContructPathologyRequestBundle}}.</p>
<br>
{{render:path-data-model-MCS-01-request}}
</div>

{{page:Home/FHIRAssets/AllAssets/All-Profiles/Examples/ExampleRenders.page.md}}