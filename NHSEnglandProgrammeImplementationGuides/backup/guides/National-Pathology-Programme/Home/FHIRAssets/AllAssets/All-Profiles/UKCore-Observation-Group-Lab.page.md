---
topic: R4ObservationTestGroup
---
## Profile: UKCore-Observation-Group-Lab (Test Group)

### Summary
A set of related tests that are reported together, for example a Full Blood Count. Test groups are often referred to as batteries, panels or profiles. The test group is represented as a FHIR <code>Observation</code> with references to other <code>Observations</code> that contain the associated test results. The references are defined using <code>Observation.hasMember</code>. 

<code>Observation.code</code> is used to represent the clinical code and name of the test group. 

<code>Observation.value[x\]</code> is not present as the test group itself does not carry a test result. 

Refer to the {{pagelink:R4ObservationTestResult}} profile definition and the {{pagelink:DesignOverview}} section for further information.

### Resource and Profile Links
* R4 Resource (Base): [Observation](https://hl7.org/fhir/R4/observation.html)
* R4 UK Core Profile (Lab): [UKCore-Observation-Group-Lab](https://simplifier.net/guide/uk-core-implementation-guide-stu2/home/profilesandextensions/profile-ukcore-observation-group-lab?current)

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
</div>

### Additional Guidance
The following table includes additional guidance that should be followed when implementing the `UKCore-Observation-Group-Lab` profile. It should be used in conjunction with the profile definition included above. Refer to {{pagelink:ProfileDescriptions}} for a definition of the table column headings.

An example of how each supported data element may be populated is provided in {{pagelink:R4SnippetsObservationTestGroup}}.

---

### `category`
TBC

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

### `note`
Comments relating to the test group.

---

### `hasMember`
Reference(s) to the `Observation(s)` that make up the test group. This may contain references to single test results, test groups (which then reference further results) or a mixture of both.

Multiple levels of test group `Observations` and test result `Observations` may be nested to support complex report structures, such as those used in Microscopy, Culture and Sensitivity (MCS) reports. Refer to the {{pagelink:DesignOverview}} section for further information.

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
            <td>The canonical URL for the <code>UKCore-Observation-LabGroup</code> profile.<br><br>This <b>SHALL</b> be populated with the following fixed value:<br><code>https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation-Group-Lab</code></td>
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
            <td>The status of the test group.</td>
        </tr>
        <tr>
            <td>category</td>
            <td>1..*</td>
            <td>1..*</td>
            <td>Mandatory</td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#CodeableConcept">CodeableConcept</a></td>
            <td>A code that classifies the general type of test group. This <b>SHALL</b> be populated with a fixed value of category code <code>laboratory</code> for <code>Laboratory</code>.<br><br>If required, additional category codes <b>MAY</b> also be included.</td>
        </tr>
	    <tr>
            <td>code</td>
            <td>1..1</td>
            <td>1..1</td>
            <td>Mandatory</td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#CodeableConcept">CodeableConcept</a></td>
            <td>The clinical code and name of the test group, for example: <code>26604007</code> <code>Full blood count</code><br><br>This <b>SHALL</b> be populated using one of the following:<br><br>
                <ul>
                    <li>memberOf 1853561000000109 | PaLM (Pathology and Laboratory Medicine) procedure simple reference set, OR</li>
                	<li>if a Procedure concept from the above reference set cannot be identified, use a SNOMED CT procedure code taken from descendantOf 386053000 | Evaluation procedure (procedure), OR</li>
                    <li>if the two methods described above fail to identify a suitable code, then it is acceptable to use a local code representing the test group</li>
                </ul>
            </td>
        </tr>
        <tr>
            <td>subject</td>
            <td>0..1</td>
            <td><code>1..1</code></td>
            <td>Mandatory</td>
            <td><a href="https://hl7.org/fhir/R4/references.html#2.3.0">Reference</a></td>
            <td>Reference to the subject that the test group relates to. This is usually (but not always) a <code>Patient</code>.</td>
        </tr>
        <tr>
            <td>effective[x]</td>
            <td>0..1</td>
            <td>0..1</td>
            <td>Required</td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#dateTime">dateTime</a> | <a href="https://hl7.org/fhir/R4/datatypes.html#Period">Period</a> | <a href="https://hl7.org/fhir/R4/datatypes.html#Timing">Timing</a> | <a href="https://hl7.org/fhir/R4/datatypes.html#instant">instant</a></td>
            <td>The date and time that the test group was performed.<br><br>The presence of <code>[x]</code> in an element name is used to indicate a <a href="https://hl7.org/fhir/R4/formats.html#choice"> choice of data type</a>. The <code>[x]</code> part of the element name is replaced with an appropriate data type, in title-case format e.g. <code>effectiveDateTime</code>.</td>
        </tr>
        <tr>
            <td>issued</td>
            <td>0..1</td>
            <td><code>1..1</code></td>
            <td>Mandatory</td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#instant">instant</a></td>
            <td>The date and time that the test group results were issued.</td>
        </tr>    
        <tr>
            <td>performer</td>
            <td>0..*</td>
            <td>0..*</td>
            <td>Required</td>
            <td><a href="https://hl7.org/fhir/R4/references.html#2.3.0">Reference</a></td>
            <td>Reference to the <code>Organization</code>, <code>Practitioner</code> or <code>PractitionerRole</code> that performed the test group.</td>
        </tr>
        <tr>
            <td>note</td>
            <td>0..*</td>
            <td>0..*</td>
            <td>Required</td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#Annotation">Annotation</a></td>
            <td>Comments relating to the test group.</td>
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
            <td>hasMember</td>
            <td>0..*</td>
            <td>0..*</td>
            <td>Required</td>
            <td><a href="https://hl7.org/fhir/R4/references.html#2.3.0">Reference</a></td>
            <td>Reference(s) to the <code>Observation(s)</code> that make up the test group. This may contain references to single test results, test groups (which then reference further results) or a mixture of both.<br><br>Multiple levels of test group <code>Observations</code> and test result <code>Observations</code> may be nested to support complex report structures, such as those used in Microscopy, Culture and Sensitivity (MCS) reports. Refer to the {{pagelink:DesignOverview}} for further information.</td>
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
        </tr>
        <tr>
            <td>encounter</td>
            <td></td>
            <td></td>
            <td></td>
            <td><a href="https://hl7.org/fhir/R4/references.html#2.3.0">Reference</a></td>
            <td>Currently out of scope - element <b>SHALL NOT</b> be populated.</td>
        </tr>
        <tr>
            <td>value[x]</td>
            <td></td>
            <td></td>
            <td></td>
            <td>Multiple</td>
            <td>Currently out of scope - element <b>SHALL NOT</b> be populated.</td>
        </tr>
        <tr>
            <td>dataAbsentReason</td>
            <td></td>
            <td></td>
            <td></td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#CodeableConcept">CodeableConcept</a></td>
            <td>Currently out of scope - element <b>SHALL NOT</b> be populated.</td>
        </tr>
        <tr>
            <td>interpretation</td>
            <td></td>
            <td></td>
            <td></td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#CodeableConcept">CodeableConcept</a></td>
            <td>Currently out of scope - element <b>SHALL NOT</b> be populated.</td>
        </tr>
        <tr>
            <td>bodysite</td>
            <td></td>
            <td></td>
            <td></td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#CodeableConcept">CodeableConcept</a></td>
            <td>Currently out of scope - element <b>SHALL NOT</b> be populated.</td>
        </tr>
        <tr>
            <td>method</td>
            <td></td>
            <td></td>
            <td></td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#CodeableConcept">CodeableConcept</a></td>
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
            <td>referenceRange</td>
            <td></td>
            <td></td>
            <td></td>
            <td><a href="https://hl7.org/fhir/R4/backboneelement.html">BackboneElement</a></td>
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
        <tr>
            <td>component</td>
            <td></td>
            <td></td>
            <td></td>
            <td><a href="https://hl7.org/fhir/R4/backboneelement.html">BackboneElement</a></td>
            <td>Currently out of scope - element <b>SHALL NOT</b> be populated.</td>
        </tr>     
    </tbody>
</table>

<br>