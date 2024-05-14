---
topic: R4ObservationTestResult
---
## Profile: UKCore-Observation-Lab (Test Result)

### Summary
An individual test result, defined as a FHIR <code>Observation</code>. The test result may be for a single test or it may form part of a test group such as a Full Blood Count.

<code>Observation.code</code> is used to represent the clinical code and name of the test.

<code>Observation.hasMember</code> is only used for <code>Observations</code> that represent test groups and is therefore out of scope for test result <code>Observations</code>. 

Refer to the {{pagelink:R4ObservationTestGroup}} profile definition and the {{pagelink:DesignOverview}} section for further information.

### Resource and Profile Links
* R4 Resource (Base): [Observation](https://hl7.org/fhir/R4/observation.html)
* R4 UK Core Profile (Lab): [UKCore-Observation-Lab](https://simplifier.net/guide/uk-core-implementation-guide-stu2/home/profilesandextensions/profile-ukcore-observation-lab?current)

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
    <b>UKCore-Observation-Lab Snippets</b> - An example to illustrate how each supported data element may be populated.<br>{{pagelink:R4SnippetsObservationTestResult}}<br><br>
    <b>Bundle Examples</b> - Various examples to illustrate the use of <code>UKCore-Observation-Lab</code> within the context of a <code>Bundle</code>.<br>{{pagelink:R4BundleExampleHbA1cReport}}<br>{{pagelink:R4BundleExampleFullBloodCountReport}}<br>{{pagelink:R4BundleExampleHBsAgReport}}<br>{{pagelink:R4BundleExampleHPVReport}}<br>{{pagelink:R4BundleExampleLipidsandHbA1cReport}}<br>{{pagelink:R4BundleExampleLFTandUandEReport}}<br>{{pagelink:R4BundleExampleGTTReport}}<br>{{pagelink:R4BundleExampleUrineMCSReport}}<br><br>
    <b>UK Core Examples</b> - Examples from the UK Core Implementation Guide.<br>
    <a href="https://simplifier.net/guide/uk-core-implementation-guide-stu2/home/examples/examplesindex/Example-UKCore-Observation-Lab-RedCellCount?current">Example UKCore-Observation-Lab-RedCellCount-Example</a><br><a href="https://simplifier.net/guide/uk-core-implementation-guide-stu2/home/examples/examplesindex/Example-UKCore-Observation-Lab-WhiteCellCount?current">Example UKCore-Observation-Lab-WhiteCellCount-Example</a><br>
</div>

### Additional Guidance
The following table includes additional guidance that should be followed when implementing the `UKCore-Observation-Lab` profile. It should be used in conjunction with the profile definition included above. Refer to {{pagelink:ProfileDescriptions}} for a definition of the table column headings.

An example of how each supported data element may be populated is provided in {{pagelink:R4SnippetsObservationTestResult}}.

---

### `category`
TBC

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

The [ValueSet](https://simplifier.net/packages/hl7.fhir.r4.core/4.0.1/files/83657) defined in FHIR is of limited benefit to UK laboratory use cases. It is therefore recommended that if a data absent reason is included, then a text representation SHOULD be used. For example: 

* `dataAbsentReason.coding.system` = `http://terminology.hl7.org/CodeSystem/data-absent-reason`
* `dataAbsentReason.coding.code` = `as-text`
* `dataAbsentReason.text` = `Specimen unsatisfactory for evaluation`

---

### `interpretation`
A coded, categorical assessment of a test result value, for example `High`. The associated test result value (i.e. `Observation.value[x]`), is usually numeric. 

Refer to the {{pagelink:DesignOverview}} section for further information relating to the representation of different types of test results.

---

### ** Previous Tabular Format **

<table class="regular">
    <thead>
        <tr>
            <th width="15%">Element Name</th>
            <th width="10%">Profile Cardinality</th>
            <th width="10%">Domain Cardinality</th>
            <th width="10%">Domain Optionality</th>
            <th width="10%">Type</th>
            <th width="45%">Definition, Constraints and Notes</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>id</td>
            <td>0..1</td>
            <td><code>1..1</code></td>
            <td>Mandatory</td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#id">id</a></td>
            <td>The logical identifier for the resource instance.</td>
        </tr>
        <tr>
            <td>meta.profile</td>
            <td>0..*</td>
            <td><code>1..1</code></td>
            <td>Mandatory</td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#uri">uri</a></td>
            <td>The canonical URL for the <code>UKCore-Observation-Lab</code> profile.<br><br>This <b>SHALL</b> be populated with the following fixed value:<br><code>https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation-Lab</code></td>
        </tr>
        <tr>
            <td>identifier</td>
            <td>0..*</td>
            <td><code>1..*</code></td>
            <td>Mandatory</td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#Identifier">Identifier</a></td>
            <td>This <b>SHALL</b> be populated with a globally unique and persistent identifier (that is, it doesn’t change between requests and is therefore stored with the source data). This <b>SHALL</b> be scoped by a provider specific namespace for the identifier.<br><br>Where consuming systems are integrating data from this resource to their local system, they <b>SHALL</b> also persist this identifier at the same time.</td>
        </tr>
        <tr>
            <td>status</td>
            <td>1..1</td>
            <td>1..1</td>
            <td>Mandatory</td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#code">code</a></td>
            <td>The status of the test result.</td>
        </tr>
        <tr>
            <td>category</td>
            <td>1..*</td>
            <td>1..*</td>
            <td>Mandatory</td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#CodeableConcept">CodeableConcept</a></td>
            <td>A code that classifies the general type of test result. This <b>SHALL</b> be populated with a fixed value of category code <code>laboratory</code> for <code>Laboratory</code>.<br><br>If required, additional category codes <b>MAY</b> also be included.</td>
        </tr>
		<tr>
            <td>code</td>
            <td>1..1</td>
            <td>1..1</td>
            <td>Mandatory</td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#CodeableConcept">CodeableConcept</a></td>
            <td>The clinical code and name of the test that was performed, for example: <code>1107451000000100</code> <code>Glucose substance concentration in serum</code><br><br>This <b>SHALL</b> be populated using one of the following:<br><br>
                <ul>
                    <li>memberOf 1853551000000106 | PaLM (Pathology and Laboratory Medicine) observable entity simple reference set, OR</li>
                    <li>memberOf 999002881000000100 | PBCL (Pathology Bounded Code List) observables simple reference set</li>
                </ul>
            </td>
        </tr>
        <tr>
            <td>subject</td>
            <td>0..1</td>
            <td><code>1..1</code></td>
            <td>Mandatory</td>
            <td><a href="https://hl7.org/fhir/R4/references.html#2.3.0">Reference</a></td>
            <td>Reference to the subject that the test relates to. This is usually (but not always) a <code>Patient</code>.</td>
        </tr>
        <tr>
            <td>effective[x]</td>
            <td>0..1</td>
            <td>0..1</td>
            <td>Required</td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#dateTime">dateTime</a> | <a href="https://hl7.org/fhir/R4/datatypes.html#Period">Period</a> | <a href="https://hl7.org/fhir/R4/datatypes.html#Timing">Timing</a> | <a href="https://hl7.org/fhir/R4/datatypes.html#instant">instant</a></td>
            <td>The date and time that the test was performed.<br><br>The presence of <code>[x]</code> in an element name is used to indicate a <a href="https://hl7.org/fhir/R4/formats.html#choice"> choice of data type</a>. The <code>[x]</code> part of the element name is replaced with an appropriate data type, in title-case format e.g. <code>effectiveDateTime</code>.</td>
        </tr>
        <tr>
            <td>issued</td>
            <td>0..1</td>
            <td><code>1..1</code></td>
            <td>Mandatory</td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#instant">instant</a></td>
            <td>The date and time that the test result was issued.</td>
        </tr>    
        <tr>
            <td>performer</td>
            <td>0..*</td>
            <td>0..*</td>
            <td>Required</td>
            <td><a href="https://hl7.org/fhir/R4/references.html#2.3.0">Reference</a></td>
            <td>Reference to the <code>Organization</code>, <code>Practitioner</code> or <code>PractitionerRole</code> that performed the test.</td>
        </tr>
        <tr>
            <td>value[x]</td>
            <td>0..1</td>
            <td>0..1</td>
            <td>Required</td>
            <td>Multiple</td>
            <td>The test result value.<br><br>The presence of <code>[x]</code> in an element name is used to indicate a <a href="https://hl7.org/fhir/R4/formats.html#choice">choice of data type</a>. The <code>[x]</code> part of the element name is replaced with an appropriate data type, in title-case format e.g. <code>valueQuantity</code>.<br><br>If the result value is a numeric quantity (i.e. a quantitative result type), a standard <a href="https://ucum.org/">UCUM</a> unit <b>SHOULD</b> be used. <br><br>If the result value is coded (i.e. a semi-quantitative or qualitative result type), a suitable SNOMED CT concept <b>SHOULD</b> be used, for example: <code>260385009</code> <code>Negative</code><br><br>Refer to the {{pagelink:DesignOverview}} section for further information relating to the representation of different types of test results.</td>
        </tr>
        <tr>
            <td>dataAbsentReason</td>
            <td>0..1</td>
            <td>0..1</td>
            <td>Required</td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#CodeableConcept">CodeableConcept</a></td>
            <td>The reason why a test result value was omitted.</td>
        </tr>
        <tr>
            <td>interpretation</td>
            <td>0..*</td>
            <td>0..*</td>
            <td>Required</td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#CodeableConcept">CodeableConcept</a></td>
            <td>A simple coded interpretation of the test result, for example <code>Detected</code>, <code>Not Detected</code>, <code>High</code>, <code>Low</code>.</td>
        </tr>
        <tr>
            <td>note</td>
            <td>0..*</td>
            <td>0..*</td>
            <td>Required</td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#Annotation">Annotation</a></td>
            <td>Comments relating to the test result.</td>
        </tr>
        <tr>
            <td>bodysite</td>
            <td>0..1</td>
            <td>0..1</td>
            <td>Required</td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#CodeableConcept">CodeableConcept</a></td>
            <td>The body part that was tested/observed.</td>
        </tr>
        <tr>
            <td>method</td>
            <td>0..1</td>
            <td>0..1</td>
            <td>Required</td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#CodeableConcept">CodeableConcept</a></td>
            <td>The method of testing/observation that was used.</td>
        </tr>     
        <tr>
            <td>specimen</td>
            <td>0..1</td>
            <td>0..1</td>
            <td>Required</td>
            <td><a href="https://hl7.org/fhir/R4/references.html#2.3.0">Reference</a></td>
            <td>Reference to the <code>Specimen</code> that was used for testing.</td>
        </tr>
        <tr>
            <td>referenceRange</td>
            <td>0..*</td>
            <td>0..*</td>
            <td>Required</td>
            <td><a href="https://hl7.org/fhir/R4/backboneelement.html">BackboneElement</a></td>
            <td>Provides a guide for interpretation of the results. Where applicable may include a low range, a high range and elements to qualify the reference range such as applicable age.</td>
        </tr>
        <tr>
            <td>component</td>
            <td>0..*</td>
            <td>0..*</td>
            <td>Required</td>
            <td><a href="https://hl7.org/fhir/R4/backboneelement.html">BackboneElement</a></td>
            <td>Used to qualify or provide additional details relating to the primary observation that the component is a part of. Components share the same attributes as the primary observation and are always treated as a part of a single observation (they are not separable). An example is the use of <code>Observation.component</code> to carry the relative time interval of a dynamic function test result. <br><br>For further information refer to:<br><br>
                <ul>
                    <li>the description of <a href="https://hl7.org/fhir/R4/observation.html#gr-comp"> Observation.component</a> in the Observation Grouping section of the base FHIR specification, and</li>
                    <li>the following example message: {{pagelink:R4BundleExampleGTTReport}}</li>
                </ul></td>
        </tr>
        <tr>
            <td>component.code</td>
            <td>1..1</td>
            <td>1..1</td>
            <td>Mandatory</td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#CodeableConcept">CodeableConcept</a></td>
            <td>The clinical code and name of the component test or qualifier.</td>
        </tr>
        <tr>
            <td>component.value[x]</td>
            <td>0..1</td>
            <td>0..1</td>
            <td>Required</td>
            <td>Multiple</td>
            <td>The component test result value.</td>
        </tr>
        <tr>
            <td>component.dataAbsentReason</td>
            <td>0..1</td>
            <td>0..1</td>
            <td>Required</td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#CodeableConcept">CodeableConcept</a></td>
            <td>The reason why a component test result value has been omitted.</td>
        </tr>
        <tr>
            <td>component.interpretation</td>
            <td>0..*</td>
            <td>0..*</td>
            <td>Required</td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#CodeableConcept">CodeableConcept</a></td>
            <td>A simple coded interpretation of the component test result, for example <code>Detected</code>, <code>Not Detected</code>, <code>High</code>, <code>Low</code>.</td>
        </tr>
        <tr>
            <td>component.referenceRange</td>
            <td>0..*</td>
            <td>0..*</td>
            <td>Required</td>
            <td><a href="https://hl7.org/fhir/R4/backboneelement.html">BackboneElement</a></td>
            <td>Provides a guide for interpretation of the results. Where applicable may include a low range, a high range and elements to qualify the reference range such as applicable age.</td>
        </tr>
        <tr>
            <td>basedOn</td>
            <td></td>
            <td></td>
            <td></td>
            <td><a href="https://hl7.org/fhir/R4/references.html#2.3.0">Reference</a></td>
            <td>Currently out of scope - element <b>SHALL NOT</b> be populated.</td>
        </tr>
        <tr>
            <td>partOf</td>
            <td></td>
            <td></td>
            <td></td>
            <td><a href="https://hl7.org/fhir/R4/references.html#2.3.0">Reference</a></td>
            <td>Currently out of scope - element <b>SHALL NOT</b> be populated.</td>
        </tr>
        <tr>
            <td>focus</td>
            <td></td>
            <td></td>
            <td></td>
            <td><a href="https://hl7.org/fhir/R4/references.html#2.3.0">Reference</a></td>
            <td>Currently out of scope - element <b>SHALL NOT</b> be populated.</td>
        <tr>
            <td>encounter</td>
            <td></td>
            <td></td>
            <td></td>
            <td><a href="https://hl7.org</b>/fhir/R4/references.html#2.3.0">Reference</a></td>
            <td>Currently out of scope - element <b>SHALL NOT</b> be populated.</td>
        </tr> 
        <tr>
            <td>device</td>
            <td></td>
            <td></td>
            <td></td>
            <td><a href="https://hl7.org/fhir/R4/references.html#2.3.0">Reference</a></td>
            <td>Currently out of scope - element <b>SHALL NOT</b> be populated.</td>
        </tr>
        <tr>
            <td>hasMember</td>
            <td></td>
            <td></td>
            <td></td>
            <td><a href="https://hl7.org/fhir/R4/references.html#2.3.0">Reference</a></td>
            <td>Currently out of scope - element <b>SHALL NOT</b> be populated.</td>
        </tr>
        <tr>
            <td>derivedFrom</td>
            <td></td>
            <td></td>
            <td></td>
            <td><a href="https://hl7.org/fhir/R4/references.html#2.3.0">Reference</a></td>
            <td>Currently out of scope - element <b>SHALL NOT</b> be populated.</td>
        </tr>
    </tbody>
</table>

<br>