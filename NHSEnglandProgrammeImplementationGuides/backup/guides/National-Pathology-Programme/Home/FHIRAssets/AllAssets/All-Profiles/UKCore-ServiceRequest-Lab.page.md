---
topic: R4ServiceRequest
---
## Profile: UKCore-ServiceRequest-Lab

### Summary
The test request that a test report is based on.

The associated test report is represented using `UKCore-DiagnosticReport-Lab` and is linked to `UKCore-ServiceRequest-Lab` using `UKCore-DiagnosticReport-Lab.basedOn`. Refer to the profile description for {{pagelink:R4DiagnosticReport}} for further information.

If multiple tests or test groups are requested as part of the same “event” (generally by the same practitioner at the same time for the same subject), an instance of `UKCore-ServiceRequest-Lab` is required for each requested test or test group. `UKCore-ServiceRequest-Lab.requisition` acts as a common identifier to link the requests.

### Resource and Profile Links
* R4 Resource (Base): [ServiceRequest](https://hl7.org/fhir/R4/servicerequest.html)
* R4 UK Core Profile: [UKCore-ServiceRequest-Lab](https://simplifier.net/guide/uk-core-implementation-guide-stu2/home/profilesandextensions/profile-ukcore-servicerequest-lab?current)

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
    {{tree: https://fhir.hl7.org.uk/StructureDefinition/UKCore-ServiceRequest-Lab, snapshot}}
</div>

<div id="Differential View" class="tabcontent">
    <h4>Differential View</h4>
    {{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-ServiceRequest-Lab, diff}}
</div>

<div id="Hybrid View" class="tabcontent">
    <h4>Hybrid View</h4>
    {{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-ServiceRequest-Lab, hybrid}}
</div>

<div id="Examples" class="tabcontent">
    <h4>Examples</h4>
    <b>UKCore-ServiceRequest-Lab Snippets</b> - An example to illustrate how each supported data element in <code>UKCore-ServiceRequest-Lab</code> may be populated.<br>{{pagelink:R4SnippetsServiceRequest}}<br><br>
    <b>Bundle Examples</b> - Examples to illustrate the use of <code>UKCore-ServiceRequest-Lab</code> within the context of a <code>Bundle</code>.<br>{{pagelink:R4BundleExampleHbA1cRequest}}<br>{{pagelink:R4BundleExampleHbA1cReport}}<br>{{pagelink:R4BundleExampleFullBloodCountRequest}}<br>{{pagelink:R4BundleExampleFullBloodCountReport}}<br>{{pagelink:R4BundleExampleHBsAgRequest}}<br>{{pagelink:R4BundleExampleHBsAgReport}}<br>{{pagelink:R4BundleExampleHPVRequest}}<br>{{pagelink:R4BundleExampleHPVReport}}<br>{{pagelink:R4BundleExampleLipidsandHbA1cRequest}}<br>{{pagelink:R4BundleExampleLipidsandHbA1cReport}}<br>{{pagelink:R4BundleExampleLFTandUandERequest}}<br>{{pagelink:R4BundleExampleLFTandUandEReport}}<br>{{pagelink:R4BundleExampleGTTRequest}}<br>{{pagelink:R4BundleExampleGTTReport}}<br>{{pagelink:R4BundleExampleUrineMCSRequest}}<br>{{pagelink:R4BundleExampleUrineMCSReport}}<br><br>
    <b>UK Core Example</b> - An example from the UK Core Implementation Guide.<br>
    <a href="https://simplifier.net/guide/uk-core-implementation-guide-stu2/home/examples/examplesindex/Example-UKCore-ServiceRequest-Lab-CReactiveProtein?current">UKCore-ServiceRequest-Lab-CReactiveProtein-Example</a><br>
</div>

### Additional Guidance
The following additional guidance **SHOULD** be applied when implementing this profile. It **SHOULD** be used in conjunction with the profile definition presented above and the Profile Specific Implementation Guidance for `UKCore-ServiceRequest-Lab` in the [UK Core Implementation Guide](https://simplifier.net/guide/uk-core-implementation-guide-stu2/home/profilesandextensions/profile-ukcore-servicerequest-lab?current).

---

### `requisition`
A shared identifier that is used to link multiple test requests.

If multiple tests or test groups are requested as part of the same “event” (generally by the same practitioner at the same time for the same subject), an instance of `ServiceRequest` is required for each requested test or test group. `ServiceRequest.requisition` acts as a common identifier to link the requests.

For further information refer to:

* the description of [Shared requisition id](https://hl7.org/FHIR/R4/request.html#requisitionid) in the Compound Requests section of the base FHIR specification, and
* the following example message: {{pagelink:R4BundleExampleLFTandUandERequest}}

---

### `status`
This **SHALL** be populated with a fixed value of `active`.

---

### `intent`
This **SHOULD** be populated with a value of `order`, unless the `ServiceRequest` relates to a reflex order i.e. a request that was initiated by a laboratory in response to the results of the originally requested test(s). In this case, a value of `reflex-order` **SHOULD** be used. For reflex orders, `ServiceRequest.basedOn` **SHALL** be populated with a reference to the original `ServiceRequest`, for traceability.

---

### `code`
The clinical code and name of the requested test or test group, for example:

* `code.coding.system` = `http://snomed.info/sct`
* `code.coding.code` = `26604007`
* `code.coding.display` = `Full blood count`

This **SHALL** be populated using one of the following:

* memberOf 1853561000000109 | PaLM (Pathology and Laboratory Medicine) procedure simple reference set, OR
* if a Procedure concept from the above reference set cannot be identified, use a SNOMED CT procedure code taken from descendantOf 386053000 | Evaluation procedure (procedure), OR
* if the two methods described above fail to identify a suitable code, then it is acceptable to use a local code representing the requested test or test group

---

### `authoredOn`
The date and time of the test request.

---

### `reasonCode`
An explanation in coded or textual form that describes why the tests have been requested.

---

### `reasonReference`
Reference(s) to any conditions the patient has (as supplied by the requester) that are relevant to the test request.

---

### `specimen`
Reference(s) to the `Specimen(s)` that will be used for testing. This should only be used when a test is requested and the specimen has already been collected.

**Note:** It is also possible to link a `Specimen` to a `ServiceRequest` using the `Specimen.request` data element. This should be used when a test was requested before the specimen was collected.

For further information refer to:

* the description of the {{pagelink:R4Specimen}} profile in this implementation guide, and
* the notes relating to the use of the [ServiceRequest](https://hl7.org/fhir/R4/servicerequest.html#notes) resource in the base FHIR specification.

---

### `note`
Any other notes relating to the test request, as provided by the requester. Clinical information relating to the test request **SHOULD** be conveyed using `ServiceRequest.reasonCode` and/or `ServiceRequest.reasonReference`.
