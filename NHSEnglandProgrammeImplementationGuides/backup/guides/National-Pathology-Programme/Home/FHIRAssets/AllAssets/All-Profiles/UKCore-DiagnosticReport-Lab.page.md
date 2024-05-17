---
topic: R4DiagnosticReport
---
## UKCore-DiagnosticReport-Lab

### Summary
A test report, containing the overall findings and clinical interpretation relating to one or more pathology tests. The report may reference individual test results, test groups or a combination of these.

Test results and test groups are defined as FHIR `Observations` (using the `UKCore-Observation-Lab` and `UKCore-Observation-Group-Lab` profiles respectively) and are referenced from `UKCore-DiagnosticReport-Lab` using `UKCore-DiagnosticReport-Lab.result`.

For information on how test results and test groups are represented, refer to the profile descriptions for {{pagelink:R4ObservationTestResult}} and {{pagelink:R4ObservationTestGroup}}. 

### Resource and Profile Links
* R4 Resource (Base): [DiagnosticReport](https://hl7.org/fhir/R4/diagnosticreport.html)
* R4 UK Core Profile: [UKCore-DiagnosticReport-Lab](https://simplifier.net/guide/uk-core-implementation-guide-stu2/home/profilesandextensions/profile-ukcore-diagnosticreport-lab?current)

### Profile Views
Refer to {{pagelink:ProfileDescriptions}} for a definition of the different profile view formats.
<div class="tab fhirTree">
    <button class="tablinks active" onclick="openTab(event, 'Snapshot View')">Snapshot View</button>
    <button class="tablinks" onclick="openTab(event, 'Differential View')">Differential View</button>
    <button class="tablinks" onclick="openTab(event, 'Hybrid View')">Hybrid View</button>
    <button class="tablinks" onclick="openTab(event, 'Examples')">Examples</button>
</div>

<div id="Snapshot View" class="tabcontent" style="display:block">
    <h4>Snapshot View</h4>
    {{tree: https://fhir.hl7.org.uk/StructureDefinition/UKCore-DiagnosticReport-Lab, snapshot}}
</div>

<div id="Differential View" class="tabcontent"></h4>
    <h4>Differential View</h4>
    {{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-DiagnosticReport-Lab, diff}}
</div>

<div id="Hybrid View" class="tabcontent">
    <h4>Hybrid View</h4>
    {{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-DiagnosticReport-Lab, hybrid}}
</div>

<div id="Examples" class="tabcontent">
    <h4>Examples</h4>
    <b>UKCore-DiagnosticReport-Lab Snippets</b> - An example to illustrate how each supported data element in <code>UKCore-DiagnosticReport-Lab</code> may be populated.<br>{{pagelink:R4SnippetsDiagnosticReport}}<br><br>
    <b>Bundle Examples</b> - Examples to illustrate the use of <code>UKCore-DiagnosticReport-Lab</code> within the context of a <code>Bundle</code>.<br>{{pagelink:R4BundleExampleHbA1cReport}}<br>{{pagelink:R4BundleExampleFullBloodCountReport}}<br>{{pagelink:R4BundleExampleHBsAgReport}}<br>{{pagelink:R4BundleExampleHPVReport}}<br>{{pagelink:R4BundleExampleLipidsandHbA1cReport}}<br>{{pagelink:R4BundleExampleLFTandUandEReport}}<br>{{pagelink:R4BundleExampleGTTReport}}<br>{{pagelink:R4BundleExampleUrineMCSReport}}<br><br>
    <b>UK Core Example</b> - An example from the UK Core Implementation Guide.<br>
    <a href="https://simplifier.net/guide/uk-core-implementation-guide-stu2/home/examples/examplesindex/Example-UKCore-DiagnosticReport-Lab-DiagnosticStudiesReport?current">UKCore-DiagnosticReport-Lab-DiagnosticStudiesReport</a><br>
</div>

### Additional Guidance
The following additional guidance **SHOULD** be applied when implementing this profile. It **SHOULD** be used in conjunction with the profile definition presented above and the Profile Specific Implementation Guidance for `UKCore-DiagnosticReport-Lab` in the [UK Core Implementation Guide](https://simplifier.net/guide/uk-core-implementation-guide-stu2/home/profilesandextensions/profile-ukcore-diagnosticreport-lab?current).

---

### `extension.noteR5`
General comments about the test report. Any information relating to the report conclusion **SHOULD** be conveyed using `DiagnosticReport.conclusion` and/or `DiagnosticReport.conclusionCode`.

Notes may be captured at a number of levels within a test report. There may also be notes related to the specimen, test group or individual test result. It is the consuming systems responsibility to make sure all relevant notes are displayed to the user.

---

### `basedOn`
Reference to the `ServiceRequest` that contains details of the test request that was made.

---

### `status`
This **SHALL** be populated as follows: 
* `partial`: when the report is issued on an initial, interim or preliminary basis, for example because some of the requested tests have not yet completed
* `final`: when the report is completed
* `unknown`: when the status is unable to be determined

---

### `category`
The general type of test report. As a minimum, the following **SHOULD** be used for this profile:

* `category.coding.system` = `http://terminology.hl7.org/CodeSystem/v2-0074`
* `category.coding.code` = `LAB`
* `category.coding.display` = `Laboratory`

This element has an open slice, and **MAY** be used to differentiate the particular speciality of the laboratory or laboratory department. This can be coded or provided as text only. For example:

* `DiagnosticReport.category.coding.text` = `Medical microbiology`

---

### `code`
This **SHALL** be populated with the following fixed value:

* `code.coding.system` = `http://snomed.info/sct`
* `code.coding.code` = `721981007`
* `code.coding.display` = `Diagnostic studies report`

**Note:** The clinical code and name of a test result or a test group is defined in the `code` element of the relevant `Observation` resource.

---

### `issued`
The date and time that the test report was issued.

---

### `result`
Reference(s) to the results included in the test report. This may contain references to individual test results, test groups or a combination of these. Test results and test groups are defined as `Observations` (using the `UKCore-Observation-Lab` and `UKCore-Observation-Group-Lab` profiles respectively).

Test results which are part of a test group will not be referenced by this element; the reference will be to the test group which will in turn reference the associated test results. Refer to the {{pagelink:DesignOverview}} section for further information.

---

### `conclusion`
A clinical interpretation/summary of the test results in a text format.

---

### `conclusionCode`
A coded finding of the test report.
