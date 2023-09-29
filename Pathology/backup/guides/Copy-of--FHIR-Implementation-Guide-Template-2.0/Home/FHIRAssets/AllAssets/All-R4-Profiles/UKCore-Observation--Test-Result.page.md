---
topic: R4ObservationTestResult
---
## R4 Profile: UKCore-Observation (Test Result)

### Summary
An individual test result, defined as an <code>Observation</code>. The test result may be for a single test or it may form part of a test group such as a Full Blood Count.

<code>Observation.code</code> is used to represent the clinical code and name of the test.

<code>Observation.hasMember</code> is only used for <code>Observations</code> that represent test groups and is therefore out of scope for test result <code>Observations</code>. 

Refer to the {{pagelink:R4ObservationTestGroup}} profile definition and the design guidance for {{pagelink:DesignRelatedTests}} for further information.

### Related Links
* R4 Resource: [Observation](https://hl7.org/fhir/R4/observation.html)<br>
* R4 UK Core Profile: [UKCore-Observation](https://simplifier.net/hl7fhirukcorer4/ukcore-observation)

### Profile Views
Refer to {{pagelink:ProfileDescriptions}} for a definition of the different profile view formats.
<div class="tab fhirTree">
    <button class="tablinks active" onclick="openTab(event, 'Snapshot View')">Snapshot View</button>
    <button class="tablinks" onclick="openTab(event, 'Differential View')">Differential View</button>
    <button class="tablinks" onclick="openTab(event, 'Hybrid View')">Hybrid View</button>
</div>

<div id="Snapshot View" class="tabcontent" style="display:block">
    <h4>Snapshot View</h4>
    {{tree: https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation, snapshot}}
</div>

<div id="Differential View" class="tabcontent">
    <h4>Differential View</h4>
    {{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation, diff}}
</div>

<div id="Hybrid View" class="tabcontent">
    <h4>Hybrid View</h4>
    {{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation, hybrid}}
</div>

### Conformance Rules
The following table describes additional conformance rules and constraints that should be applied when implementing the `UKCore-Observation` profile as part of this specification. It should be used in conjunction with the profile definition included above. Refer to {{pagelink:ProfileDescriptions}} for a definition of the table column headings.

An example of how each supported data element may be populated is provided in {{pagelink:R4SnippetsObservationTestResult}}.

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
            <td>The URL for the <code>UKCore-Observation</code> profile.<br><br>This <b>SHALL</b> be populated with the following fixed value:<br><code>https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation</code></td>
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
            <td>0..*</td>
            <td>0..*</td>
            <td>Required</td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#CodeableConcept">CodeableConcept</a></td>
            <td>The general type of test result. This <b>SHOULD</b> be populated with a default code of <code>laboratory</code>.</td>
        </tr>
		<tr>
            <td>code</td>
            <td>1..1</td>
            <td>1..1</td>
            <td>Mandatory</td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#CodeableConcept">CodeableConcept</a></td>
            <td>The clinical code and name of the test that was performed, for example: <code>1107451000000100</code> <code>Glucose substance concentration in serum</code><br><br>This <b>SHOULD</b> be populated with a SNOMED CT observable entity code and description, selected from the following:<br><br>
                <ul>
                    <li>memberOf 1853551000000106 | Palm (pathology and laboratory medicine) observable entity simple reference set</li>
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
            <td>The test result value.<br><br>The presence of <code>[x]</code> in an element name is used to indicate a <a href="https://hl7.org/fhir/R4/formats.html#choice">choice of data type</a>. The <code>[x]</code> part of the element name is replaced with an appropriate data type, in title-case format e.g. <code>valueQuantity</code>.<br><br>If the result value is a numeric quantity, a standard <a href="https://ucum.org/">UCUM</a> unit <b>SHOULD</b> be used.</td>
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
            <td>0..1</td>
            <td>0..1</td>
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
            <td>Used to qualify or provide additional details relating to the primary observation that the component is a part of. Components share the same attributes as the primary observation and are always treated as a part of a single observation (they are not separable). An example is the use of <code>Observation.component</code> to carry the relative time interval of a dynamic function test result. <br><br>For further information refer to: 
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
            <td>0</td>
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