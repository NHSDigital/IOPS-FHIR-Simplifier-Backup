---
topic: R4BundleExampleUrineMCSReport
subject: Pathology-Bundle-Urine-MCS-01-Report-Example
---
### PATH-R4-16: R4 Bundle Example - Urine Microscopy, Culture and Sensitivity Report

{{page:Home/FHIRAssets/AllAssets/All-Profiles/Examples/ExampleTabs.page.md}}
    
        <div id="Example" role="tabpanel" class="tabcontent"  style="display:block"> 
{{render:path-mockup-MCS-01-report}}
        </div>
        <div id="Notes" role="tabpanel" class="tabcontent">
            <br>
			<ul>
                <li>This is an example of a complex report.</li>
                <li>It contains multiple levels of test group <code>Observations</code> and test result <code>Observations</code>. Two of the test groups are nested ("Urine Culture" and "Antimicrobial sensitivity").</li>
                <li>The report includes a range of numeric, semi-quantitative and qualitative results.</li>
                <li>In this example, the specimen (urine) was collected after the request was made. The specimen is linked to the request within the <code>Bundle</code> using <code>Specimen.request</code>.</li>
            </ul>
        </div>
        <div id="DataModel" role="tabpanel" class="tabcontent">
            <br>
            <p>The following is a simplified logical data model that illustrates the key references between the FHIR profiles in the example message bundle. To aid clarity, not all of the references are shown. For a detailed description of the relationships between the FHIR profiles, and how they may be used, refer to {{pagelink:BuildContructPathologyReportBundle}}.</p>
            <br>
            {{render:path-data-model-MCS-01-report}}
        </div>

{{page:Home/FHIRAssets/AllAssets/All-Profiles/Examples/ExampleRenders.page.md}}