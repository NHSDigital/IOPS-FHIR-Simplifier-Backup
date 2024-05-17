---
topic: R4ObservationTestGroup
---
## UKCore-Observation-Group-Lab (Test Group)

### Summary
A set of related tests that are reported together, for example a Full Blood Count. Test groups are often referred to as batteries, panels or profiles. 

The test group is represented using `UKCore-Observation-Group-Lab` with references to instances of `UKCore-Observation-Lab` that contain the associated test results. The references are defined using `UKCore-Observation-Group-Lab.hasMember`. 

`UKCore-Observation-Group-Lab.code` is used to represent the clinical code and name of the test group. 

`UKCore-Observation-Group-Lab.value[x]` is not used as a test group does not carry a test result. 

Refer to the {{pagelink:R4ObservationTestResult}} profile definition and the {{pagelink:DesignOverview}} section for further information.

### Resource and Profile Links
* R4 Resource (Base): [Observation](https://hl7.org/fhir/R4/observation.html)
* R4 UK Core Profile: [UKCore-Observation-Group-Lab](https://simplifier.net/guide/uk-core-implementation-guide-stu2/home/profilesandextensions/profile-ukcore-observation-group-lab?current)

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
    {{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation-Group-Lab, snapshot}}
</div>

<div id="Differential View" class="tabcontent">
    <h4>Differential View</h4>
    {{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation-Group-Lab, diff}}
</div>

<div id="Hybrid View" class="tabcontent">
    <h4>Hybrid View</h4>
    {{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation-Group-Lab, hybrid}}
</div>

<div id="Examples" class="tabcontent">
    <h4>Examples</h4>
    <b>UKCore-Observation-Group-Lab Snippets</b> - An example to illustrate how each supported data element in <code>UKCore-Observation-Group-Lab</code> may be populated.<br>{{pagelink:R4SnippetsObservationTestGroup}}<br><br>
    <b>Bundle Examples</b> - Examples to illustrate the use of <code>UKCore-Observation-Group-Lab</code> within the context of a <code>Bundle</code>.<br>{{pagelink:R4BundleExampleFullBloodCountReport}}<br>{{pagelink:R4BundleExampleLipidsandHbA1cReport}}<br>{{pagelink:R4BundleExampleLFTandUandEReport}}<br>{{pagelink:R4BundleExampleGTTReport}}<br>{{pagelink:R4BundleExampleUrineMCSReport}}<br><br>
    <b>UK Core Example</b> - An example from the UK Core Implementation Guide.<br>
    <a href="https://simplifier.net/guide/uk-core-implementation-guide-stu2/Home/Examples/ExamplesIndex/Example-UKCore-Observation-Group-FullBloodCount?current">UKCore-Observation-Group-FullBloodCount-Example</a><br>
</div>

### Additional Guidance
The following additional guidance **SHOULD** be applied when implementing this profile. It **SHOULD** be used in conjunction with the profile definition presented above and the Profile Specific Implementation Guidance for `UKCore-Observation-Group-Lab` in the [UK Core Implementation Guide](https://simplifier.net/guide/uk-core-implementation-guide-stu2/home/profilesandextensions/profile-ukcore-observation-group-lab?current).

---

### `category`
The general type of test group. As a minimum, the following **SHOULD** be used for this profile:

* `category.coding.system` = `http://terminology.hl7.org/CodeSystem/observation-category`
* `category.coding.code` = `laboratory`
* `category.coding.display` = `Laboratory`

This element has an open slice, and **MAY** be used to differentiate the particular test speciality. This can be coded or provided as text only.

---

### `code`
The clinical code and name of the test group, for example:

* `code.coding.system` = `http://snomed.info/sct`
* `code.coding.code` = `26604007`
* `code.coding.display` = `Full blood count`

This **SHALL** be populated using one of the following:

* memberOf 1853561000000109 | PaLM (Pathology and Laboratory Medicine) procedure simple reference set, OR
* if a Procedure concept from the above reference set cannot be identified, use a SNOMED CT procedure code taken from descendantOf 386053000 | Evaluation procedure (procedure), OR
* if the two methods described above fail to identify a suitable code, then it is acceptable to use a local code representing the test group

---

### `effective[x]`
The date and time that the test group was performed.

The presence of `[x]` in an element name is used to indicate a [choice of data type](https://hl7.org/fhir/R4/formats.html#choice). The `[x]` part of the element name is replaced with an appropriate data type, in title-case format e.g. `effectiveDateTime`.

---

### `issued`
The date and time that the test group results were issued.

---

### `value[x]`
This element **SHOULD NOT** be used within this profile as a test group does not carry a test result.

---

### `note`
Comments relating to the test group.

---

### `hasMember`
Reference(s) to the `Observation(s)` that make up the test group. This may contain references to single test results (using the `UKCore-Observation-Lab` profile), test groups (using the `UKCore-Observation-Group-Lab` profile) or a mixture of both.

Multiple levels of test group `Observations` and test result `Observations` may be nested to support complex report structures, such as those used in Microscopy, Culture and Sensitivity (MCS) reports. Refer to the {{pagelink:DesignOverview}} section for further information.
