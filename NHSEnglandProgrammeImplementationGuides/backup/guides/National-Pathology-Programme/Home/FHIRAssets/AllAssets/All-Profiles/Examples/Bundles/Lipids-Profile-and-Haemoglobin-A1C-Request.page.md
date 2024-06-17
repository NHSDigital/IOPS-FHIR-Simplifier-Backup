---
topic: R4BundleExampleLipidsandHbA1cRequest
subject: Pathology-Bundle-Lipids-HbA1c-Request-Example
---
### PATH-R4-11: Bundle Example - Lipids Profile and Haemoglobin A1c (HbA1c) Request

{{page:Home/FHIRAssets/AllAssets/All-Profiles/Examples/ExampleTabs.page.md}}

<div id="Example" role="tabpanel" class="tabcontent"  style="display:block"> 
   {{render:path-mockup-lipids-HbA1c-request}}
</div>
<div id="Notes" role="tabpanel" class="tabcontent">
    <br>
    <ul>
        <li>This is an example of a request for a single test group and a single test.</li>
        <li>In this example, the tests are being requested as part of the same “event” (i.e. by the same practitioner at the same time for the same subject).</li>
        <li>An instance of <code>ServiceRequest</code> is required for the test group and a separate instance of <code>ServiceRequest</code> is required for the single test. <b>Note: </b> <code>ServiceRequest.code</code>, which is used to specify the requested test, has a cardinality of 0..1.</li>
        <li>Each <code>ServiceRequest</code> within a set of related requests uses a common identifier, <code>ServiceRequest.requisition</code>, to link them together. For further information, refer to the description of the {{pagelink:R4ServiceRequest}} profile.</li>
    </ul>
</div>
<div id="DataModel" role="tabpanel" class="tabcontent">
    <br>
    <p>The following is a simplified logical data model that illustrates the key references between the FHIR profiles in the example message bundle. To aid clarity, not all of the references are shown. For a detailed description of the relationships between the FHIR profiles, and how they may be used, refer to {{pagelink:BuildContructPathologyRequestBundle}}.</p>
    <br>
    {{render:path-data-model-lipids-HbA1c-request}}
</div>

{{page:Home/FHIRAssets/AllAssets/All-Profiles/Examples/ExampleRenders.page.md}}