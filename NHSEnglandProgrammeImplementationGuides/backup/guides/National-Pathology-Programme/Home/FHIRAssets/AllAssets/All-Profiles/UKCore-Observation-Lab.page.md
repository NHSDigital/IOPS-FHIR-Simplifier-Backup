---
topic: R4ObservationTestResult
---
## UKCore-Observation-Lab (Test Result)

### Summary
An individual test result, represented using `UKCore-Observation-Lab`. The test result may be for a single test or it may form part of a test group such as a Full Blood Count.

`UKCore-Observation-Lab.code` is used to represent the clinical code and name of the test.

`UKCore-Observation-Lab.hasMember` is not used as this profile is used to represent a test result rather than a test group. Where an `Observation` is being used to represent a test group (with `Observation.hasMember` references), then `UKCore-Observation-Group-Lab` should be used instead.

Refer to the {{pagelink:R4ObservationTestGroup}} profile definition and the {{pagelink:DesignOverview}} section for further information.

### Resource and Profile Links
* R4 Resource (Base): [Observation](https://hl7.org/fhir/R4/observation.html)
* R4 UK Core Profile: [UKCore-Observation-Lab](https://simplifier.net/guide/uk-core-implementation-guide-stu2/home/profilesandextensions/profile-ukcore-observation-lab?current)

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
    {{tree: https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation-Lab, snapshot}}
</div>

<div id="Differential View" class="tabcontent">
    <h4>Differential View</h4>
    {{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation-Lab, diff}}
</div>

<div id="Hybrid View" class="tabcontent">
    <h4>Hybrid View</h4>
    {{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation-Lab, hybrid}}
</div>

<div id="Examples" class="tabcontent">
    <h4>Examples</h4>
    <b>UKCore-Observation-Lab Snippets</b> - An example to illustrate how each supported data element in <code>UKCore-Observation-Lab</code> may be populated.<br>{{pagelink:R4SnippetsObservationTestResult}}<br><br>
    <b>Bundle Examples</b> - Examples to illustrate the use of <code>UKCore-Observation-Lab</code> within the context of a <code>Bundle</code>.<br>{{pagelink:R4BundleExampleHbA1cReport}}<br>{{pagelink:R4BundleExampleFullBloodCountReport}}<br>{{pagelink:R4BundleExampleHBsAgReport}}<br>{{pagelink:R4BundleExampleHPVReport}}<br>{{pagelink:R4BundleExampleLipidsandHbA1cReport}}<br>{{pagelink:R4BundleExampleLFTandUandEReport}}<br>{{pagelink:R4BundleExampleGTTReport}}<br>{{pagelink:R4BundleExampleUrineMCSReport}}<br><br>    
    <b>Observation Examples (Quantitative)</b> - Examples to illustrate the use of <code>UKCore-Observation-Lab</code> for quantitative (i.e. numeric) test results.<br>{{pagelink:R4ObservationAlbumin}}<br>{{pagelink:R4ObservationeGFR}}<br><br>
    <b>Observation Examples (Semi-quantitative)</b> - Examples to illustrate the use of <code>UKCore-Observation-Lab</code> for semi-quantitative test results.<br>{{pagelink:R4ObservationEpithelialCells}}<br>{{pagelink:R4ObservationNitrofurantoinSusceptibility}}<br><br> 
    <b>Observation Examples (Qualitative)</b> - Examples to illustrate the use of <code>UKCore-Observation-Lab</code> for qualitative test results.<br>{{pagelink:R4ObservationHBsAg}}<br>{{pagelink:R4ObservationMRSAScreeningTest}}<br><br>
    <b>Observation Example (Narrative)</b> - An example to illustrate the use of <code>UKCore-Observation-Lab</code> for a narrative (i.e. text-based) test result.<br>{{pagelink:R4ObservationAerobicBloodCulture}}<br><br>
    <b>UK Core Examples</b> - Examples from the UK Core Implementation Guide.<br>
    <a href="https://simplifier.net/guide/uk-core-implementation-guide-stu2/home/examples/examplesindex/Example-UKCore-Observation-Lab-RedCellCount?current">UKCore-Observation-Lab-RedCellCount-Example</a><br><a href="https://simplifier.net/guide/uk-core-implementation-guide-stu2/home/examples/examplesindex/Example-UKCore-Observation-Lab-WhiteCellCount?current">UKCore-Observation-Lab-WhiteCellCount-Example</a><br>
</div>

### Additional Guidance
The following additional guidance **SHOULD** be applied when implementing this profile. It **SHOULD** be used in conjunction with the profile definition presented above and the Profile Specific Implementation Guidance for `UKCore-Observation-Lab` in the [UK Core Implementation Guide](https://simplifier.net/guide/uk-core-implementation-guide-stu2/home/profilesandextensions/profile-ukcore-observation-lab?current).

---

### `category`
The general type of test. As a minimum, the following **SHOULD** be used for this profile:

* `category.coding.system` = `http://terminology.hl7.org/CodeSystem/observation-category`
* `category.coding.code` = `laboratory`
* `category.coding.display` = `Laboratory`

This element has an open slice, and **MAY** be used to differentiate the particular test speciality. This can be coded or provided as text only.

---

### `code`
The clinical code and name of the test that was performed, for example:

* `code.coding.system` = `http://snomed.info/sct`
* `code.coding.code` = `1107451000000100`
* `code.coding.display` = `Glucose substance concentration in serum`

This **SHALL** be populated using one of the following:

* memberOf 1853551000000106 | PaLM (Pathology and Laboratory Medicine) observable entity simple reference set, OR
* memberOf 999002881000000100 | PBCL (Pathology Bounded Code List) observables simple reference set

---

### `effective[x]`
The date and time that the test was performed.

The presence of `[x]` in an element name is used to indicate a [choice of data type](https://hl7.org/fhir/R4/formats.html#choice). The `[x]` part of the element name is replaced with an appropriate data type, in title-case format e.g. `effectiveDateTime`.

---

### `issued`
The date and time that the test result was issued.

---

### `value[x]`
The test result value.

The presence of `[x]` in an element name is used to indicate a [choice of data type](https://hl7.org/fhir/R4/formats.html#choice). The `[x]` part of the element name is replaced with an appropriate data type, in title-case format e.g. `valueQuantity`.

If the result value is a numeric quantity (i.e. a quantitative result type), a standard [UCUM](https://ucum.org/) **SHOULD** be used.

If the result value is coded (i.e. a semi-quantitative or qualitative result type), a suitable SNOMED CT concept **SHOULD** be used, for example: 

* `valueCodeableConcept.coding.system` = `http://snomed.info/sct`
* `valueCodeableConcept.coding.code` = `260385009"`
* `valueCodeableConcept.coding.display` = `Negative`

Refer to the {{pagelink:DesignOverview}} section for further information relating to the representation of different types of test results.

---

### `dataAbsentReason`
The reason why a test result value was omitted.

The [ValueSet](https://simplifier.net/packages/hl7.fhir.r4.core/4.0.1/files/83657) defined in FHIR is of limited benefit to UK laboratory use cases. It is therefore recommended that if a data absent reason is included, then a text representation **SHOULD** be used. For example: 

* `dataAbsentReason.coding.system` = `http://terminology.hl7.org/CodeSystem/data-absent-reason`
* `dataAbsentReason.coding.code` = `as-text`
* `dataAbsentReason.text` = `Specimen unsatisfactory for evaluation`

---

### `interpretation`
A coded, categorical assessment of a test result value, for example `High`. The associated test result value (i.e. `Observation.value[x]`), is usually numeric. 

Refer to the {{pagelink:DesignOverview}} section for further information relating to the representation of different types of test results.

---

### `hasMember`
This element **SHOULD NOT** be used as this profile is used to represent individual test results. Where an `Observation` is being used to represent a group of tests (with `Observation.hasMember` references), then the {{pagelink:R4ObservationTestGroup}} profile **SHOULD** be used instead.
