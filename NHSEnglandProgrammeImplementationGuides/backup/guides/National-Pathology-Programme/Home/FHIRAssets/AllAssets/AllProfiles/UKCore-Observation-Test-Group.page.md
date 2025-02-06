---
topic: R4ObservationTestGroup
---
## UKCore-Observation (Test Group)

### Summary
A test group, represented using `UKCore-Observation`.
Within this implementation guide, a test group is defined as a set of related tests that are reported together, for example a Full Blood Count. Test groups are more widely referred to as batteries, panels or profiles. 

When used to represent a test group, `UKCore-Observation` includes references to other instances of `UKCore-Observation` that contain the associated test results. The references are defined using `UKCore-Observation.hasMember`.

Refer to {{pagelink:R4ObservationTestResult}} for a description of how `UKCore-Observation` is used to represent a test result.

### Resource and Profile Links
* R4 Resource (Base): [Observation](https://hl7.org/fhir/R4/observation.html)
* R4 UK Core Profile: [UKCore-Observation](https://simplifier.net/guide/uk-core-implementation-guide-stu2/home/profilesandextensions/profile-ukcore-observation?current)

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
    {{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation, snapshot}}
</div>

<div id="Differential View" class="tabcontent">
    <h4>Differential View</h4>
    {{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation, diff}}
</div>

<div id="Hybrid View" class="tabcontent">
    <h4>Hybrid View</h4>
    {{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation, hybrid}}
</div>

<div id="Examples" class="tabcontent">
    <h4>Examples</h4>
    <b>UKCore-Observation-Snippets</b> - An example to illustrate how each key data element in <code>UKCore-Observation</code> may be populated for a test group.<br>{{pagelink:R4SnippetsObservationTestGroup}}<br><br>
    <b>Bundle Examples</b> - Examples to illustrate the use of <code>UKCore-Observation</code> for a test group within the context of a <code>Bundle</code>.<br>{{pagelink:R4BundleExampleFullBloodCountReport}}<br>{{pagelink:R4BundleExampleLipidsandHbA1cReport}}<br>{{pagelink:R4BundleExampleLFTandUandEReport}}<br>{{pagelink:R4BundleExampleGTTReportUnstructured}}<br>{{pagelink:R4BundleExampleGTTReportStructured}}<br>{{pagelink:R4BundleExampleUrineMCSReportUnstructured}}<br>{{pagelink:R4BundleExampleUrineMCSReportStructured}}<br>
</div>

### Additional Guidance
The following additional guidance **SHOULD** be applied when implementing this profile. It **SHOULD** be used in conjunction with the profile definition presented above and the Profile Specific Implementation Guidance for `UKCore-Observation` in the [UK Core Implementation Guide](https://simplifier.net/guide/uk-core-implementation-guide-stu2/home/profilesandextensions/profile-ukcore-observation?current).

---

### `category`
The general type of test group. As a minimum, the following **SHOULD** be used for this profile:

* `Observation.category.coding.system` = `http://terminology.hl7.org/CodeSystem/observation-category`
* `Observation.category.coding.code` = `laboratory`
* `Observation.category.coding.display` = `Laboratory`

This element has an open slice, and **MAY** be used to differentiate the particular test speciality. This can be coded or provided as text only.

---

### `code`
The clinical code and name of the test group, for example:

* `Observation.code.coding.system` = `http://snomed.info/sct`
* `Observation.code.coding.code` = `26604007`
* `Observation.code.coding.display` = `Full blood count`

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
This element **SHOULD NOT** be used as a test group `Observation` does not directly carry a test result.  The results are conveyed in the test result `Observations` that the test group references.

---

### `note`
Comments relating to the test group.

---

### `hasMember`
Reference(s) to the `Observation(s)` that make up the test group. This may contain references to single test results, test groups or a mixture of both.

Multiple levels of test group `Observations` and test result `Observations` may be nested to support complex report structures, such as those used in Microscopy, Culture and Sensitivity (MC&S) reports. Refer to the {{pagelink:DesignOverview}} section for further information.
