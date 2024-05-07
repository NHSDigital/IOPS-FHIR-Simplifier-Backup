---
topic: R4ServiceRequest
---
## Profile: UKCore-ServiceRequest-Lab

### Summary
The test request that a test report is based on.

The associated test report is represented as a FHIR <code>DiagnosticReport</code> and is linked to <code>ServiceRequest</code> using <code>DiagnosticReport.basedOn</code>. Refer to the profile description for {{pagelink:R4DiagnosticReport}} for further information.

If multiple tests or test groups are requested as part of the same “event” (generally by the same practitioner at the same time for the same subject), an instance of <code>ServiceRequest</code> is required for each requested test or test group. <code>ServiceRequest.requisition</code> acts as a common identifier to link the requests.

### Resource and Profile Links
* R4 Resource (Base): [ServiceRequest](https://hl7.org/fhir/R4/servicerequest.html)
* R4 UK Core Profile (Lab): [UKCore-ServiceRequest-Lab](https://simplifier.net/guide/uk-core-implementation-guide-stu2/home/profilesandextensions/profile-ukcore-servicerequest-lab?current)

### Profile Views
Refer to {{pagelink:ProfileDescriptions}} for a definition of the different profile view formats.
<div class="tab fhirTree">
    <button class="tablinks active" onclick="openTab(event, 'Snapshot View')">Snapshot View</button>
    <button class="tablinks" onclick="openTab(event, 'Differential View')">Differential View</button>
    <button class="tablinks" onclick="openTab(event, 'Hybrid View')">Hybrid View</button>
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

### Additional Guidance
The following table includes additional guidance that should be followed when implementing the `UKCore-ServiceRequest-Lab` profile. It should be used in conjunction with the profile definition included above. Refer to {{pagelink:ProfileDescriptions}} for a definition of the table column headings.

An example of how each supported data element may be populated is provided in {{pagelink:R4SnippetsServiceRequest}}.

---

### `requisition`

A shared identifier that is used to link multiple test requests.

If multiple tests or test groups are requested as part of the same “event” (generally by the same practitioner at the same time for the same subject), an instance of `ServiceRequest` is required for each requested test or test group. `ServiceRequest.requisition` acts as a common identifier to link the requests.

For further information refer to:

* the description of [Shared requisition id](https://hl7.org/FHIR/R4/request.html#requisitionid) in the Compound Requests section of the base FHIR specification, and
* the following example message: {{pagelink:R4BundleExampleLFTandUandERequest}}

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

### `category`

TBC

---

### `code'

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

---

### ** Previous Table Format **

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
            <td>The canonical URL for the <code>UKCore-ServiceRequest-Lab</code> profile.<br><br>This <b>SHALL</b> be populated with the following fixed value:<br><code>https://fhir.hl7.org.uk/StructureDefinition/UKCore-ServiceRequest-Lab</code></td>
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
            <td>requisition</td>
            <td>0..1</td>
            <td>0..1</td>
            <td>Optional</td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#Identifier">Identifier</a></td>
            <td>A shared identifier that is used to link multiple test requests.<br><br>If multiple tests or test groups are requested as part of the same “event” (generally by the same practitioner at the same time for the same subject), an instance of <code>ServiceRequest</code> is required for each requested test or test group. <code>ServiceRequest.requisition</code> acts as a common identifier to link the requests.<br><br>For further information refer to:<br><br>
                <ul>
                    <li>the description of <a href="https://hl7.org/FHIR/R4/request.html#requisitionid"> Shared requisition id</a> in the Compound Requests section of the base FHIR specification, and</li>
                    <li>the following example message: {{pagelink:R4BundleExampleLFTandUandERequest}}</li>
                </ul>
            </td>
        </tr>
        <tr>
            <td>status</td>
            <td>1..1</td>
            <td>1..1</td>
            <td>Mandatory</td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#code">code</a></td>
            <td>This <b>SHALL</b> be populated with a fixed value of <code>active</code>.</td>
        </tr>
        <tr>
            <td>intent</td>
            <td>1..1</td>
            <td>1..1</td>
            <td>Mandatory</td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#code">code</a></td>
            <td>This <b>SHALL</b> be populated with a fixed value of <code>order</code>.</td>
        </tr>
        <tr>
            <td>priority</td>
            <td>0..1</td>
            <td>0..1</td>
            <td>Required</td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#code">code</a></td>
            <td>The urgency of the test request.</td>
        </tr>
		<tr>
            <td>code</td>
            <td>0..1</td>
            <td><code>1..1</code></td>
            <td>Mandatory</td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#CodeableConcept">CodeableConcept</a></td>
            <td>The clinical code and name of the requested test or test group, for example: <code>26604007</code> <code>Full blood count</code><br><br>This <b>SHALL</b> be populated using one of the following:<br><br>
                <ul>
                    <li>memberOf 1853561000000109 | PaLM (Pathology and Laboratory Medicine) procedure simple reference set, OR</li>
                    <li>if a Procedure concept from the above reference set cannot be identified, use a SNOMED CT procedure code taken from descendantOf 386053000 | Evaluation procedure (procedure), OR</li>
                    <li>if the two methods described above fail to identify a suitable code, then it is acceptable to use a local code representing the requested test or test group</li>
                </ul>
            </td>
        </tr>
        <tr>
            <td>subject</td>
            <td>1..1</td>
            <td>1..1</td>
            <td>Mandatory</td>
            <td><a href="https://hl7.org/fhir/R4/references.html#2.3.0">Reference</a></td>
            <td>Reference to the subject that the test request relates to. This is usually (but not always) a <code>Patient</code>.</td>
        </tr>
        <tr>
            <td>authoredOn</td>
            <td>0..1</td>
            <td>0..1</td>
            <td>Required</td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#dateTime">dateTime</a></td>
            <td>The date and time of the test request.</td>
        </tr>
        <tr>
            <td>requester</td>
            <td>0..1</td>
            <td>0..1</td>
            <td>Required</td>
            <td><a href="https://hl7.org/fhir/R4/references.html#2.3.0">Reference</a></td>
            <td>Reference to the <code>Organization</code>, <code>Practitioner</code> or <code>PractitionerRole</code> that requested the test(s).</td>
        </tr>
        <tr>
            <td>performer</td>
            <td>0..*</td>
            <td>0..*</td>
            <td>Required</td>
            <td><a href="https://hl7.org/fhir/R4/references.html#2.3.0">Reference</a></td>
            <td>Reference to the <code>Organization</code>, <code>Practitioner</code> or <code>PractitionerRole</code> that has been requested to perform the test(s).</td>
        </tr>
        <tr>
            <td>reasonCode</td>
            <td>0..*</td>
            <td>0..*</td>
            <td>Required</td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#CodeableConcept">CodeableConcept</a></td>
            <td>An explanation in coded or textual form that describes why the tests have been requested.</td>
        </tr>
        <tr>
            <td>reasonReference</td>
            <td>0..*</td>
            <td>0..*</td>
            <td>Required</td>
            <td><a href="https://hl7.org/fhir/R4/references.html#2.3.0">Reference</a></td>
            <td>Reference(s) to any conditions the patient has (as supplied by the requester) that are relevant to the test request.</td>
        </tr>
        <tr>
            <td>specimen</td>
            <td>0..*</td>
            <td>0..*</td>
            <td>Required</td>
            <td><a href="https://hl7.org/fhir/R4/references.html#2.3.0">Reference</a></td>
            <td>Reference(s) to the <code>Specimen(s)</code> that will be used for testing. This should only be used when a test is requested and the specimen has already been collected.<br><br><b>Note:</b> It is also possible to link a <code>Specimen</code> to a <code>ServiceRequest</code> using the <code>Specimen.request</code> data element. This should be used when a test was requested before the specimen was collected.<br><br>For further information refer to:<br><br>
                <ul>
                    <li>the description of the {{pagelink:R4Specimen}} profile in this implementation guide, and</li>
                    <li>the notes relating to the use of the<a href="https://hl7.org/fhir/R4/servicerequest.html#notes"> ServiceRequest</a> resource in the base FHIR specification.</li>
                </ul>
            </td>
        </tr>  
        <tr>
            <td>note</td>
            <td>0..*</td>
            <td>0..*</td>
            <td>Required</td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#annotation">Annotation</a></td>
            <td>Any other notes relating to the test request, as provided by the requester. Clinical information relating to the test request SHOULD be conveyed using <code>ServiceRequest.reasonCode</code> and/or <code>ServiceRequest.reasonReference</code>.</td>
        </tr>
        <tr>
            <td>extension (sourceOfServiceRequest)</td>
            <td></td>
            <td></td>
            <td></td>
            <td><a href="https://hl7.org/fhir/R4/extensibility.html#Extension">Extension</a></td>
            <td>Currently out of scope - element <b>SHALL NOT</b> be populated.</td>
        </tr>
        <tr>
            <td>instantiatesCanonical</td>
            <td></td>
            <td></td>
            <td></td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#canonical">canonical</a>(<a href="https://hl7.org/fhir/R4/activitydefinition.html">ActivityDefinition</a> | <a href="https://hl7.org/fhir/R4/plandefinition.html">PlanDefinition)</a></td>
            <td>Currently out of scope - element <b>SHALL NOT</b> be populated.</td>
        </tr
        <tr>
            <td>instantiatesUri</td>
            <td></td>
            <td></td>
            <td></td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#uri">uri</a></td>
            <td>Currently out of scope - element <b>SHALL NOT</b> be populated.</td>
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
            <td>replaces</td>
            <td></td>
            <td></td>
            <td></td>
            <td><a href="https://hl7.org/fhir/R4/references.html#2.3.0">Reference</a></td>
            <td>Currently out of scope - element <b>SHALL NOT</b> be populated.</td>
        </tr>
        <tr>
            <td>category</td>
            <td></td>
            <td></td>
            <td></td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#CodeableConcept">CodeableConcept</a></td>
            <td>Currently out of scope - element <b>SHALL NOT</b> be populated.</td>
        </tr>
        <tr>
            <td>doNotPerform</td>
            <td></td>
            <td></td>
            <td></td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#boolean">boolean</a></td>
            <td>Currently out of scope - element <b>SHALL NOT</b> be populated.</td>
        </tr>
        <tr>
            <td>orderDetail</td>
            <td></td>
            <td></td>
            <td></td>
  <td><a href="https://hl7.org/fhir/R4/datatypes.html#CodeableConcept">CodeableConcept</a></td>
            <td>Currently out of scope - element <b>SHALL NOT</b> be populated.</td>
        </tr>
        <tr>
            <td>quantity[x]</td>
            <td></td>
            <td></td>
            <td></td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#Quantity">Quantity</a> | <a href="https://hl7.org/fhir/R4/datatypes.html#Ratio">Ratio</a> | <a href="https://hl7.org/fhir/R4/datatypes.html#Range">Range</a></td>
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
            <td>occurrence[x]</td>
            <td></td>
            <td></td>
            <td></td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#dateTime">dateTime</a> | <a href="https://hl7.org/fhir/R4/datatypes.html#Period">Period</a> | <a href="https://hl7.org/fhir/R4/datatypes.html#Timing">Timing</a></td>
            <td>Currently out of scope - element <b>SHALL NOT</b> be populated.</td>
        </tr>
        <tr>
            <td>asNeeded[x]</td>
            <td></td>
            <td></td>
            <td></td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#boolean">boolean</a> | <a href="https://hl7.org/fhir/R4/datatypes.html#CodeableConcept">CodeableConcept</a></td>
            <td>Currently out of scope - element <b>SHALL NOT</b> be populated.</td>
        </tr>
        <tr>
            <td>performerType</td>
            <td></td>
            <td></td>
            <td></td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#CodeableConcept">CodeableConcept</a></td>
            <td>Currently out of scope - element <b>SHALL NOT</b> be populated.</td>
        </tr>
        <tr>
            <td>locationCode</td>
            <td></td>
            <td></td>
            <td></td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#CodeableConcept">CodeableConcept</a></td>
            <td>Currently out of scope - element <b>SHALL NOT</b> be populated.</td>
        </tr>
        <tr>
            <td>locationReference</td>
            <td></td>
            <td></td>
            <td></td>
            <td><a href="https://hl7.org/fhir/R4/references.html#2.3.0">Reference</a></td>
            <td>Currently out of scope - element <b>SHALL NOT</b> be populated.</td>
        </tr>
        <tr>
            <td>insurance</td>
            <td></td>
            <td></td>
            <td></td>
            <td><a href="https://hl7.org/fhir/R4/references.html#2.3.0">Reference</a></td>
            <td>Currently out of scope - element <b>SHALL NOT</b> be populated.</td>
        </tr>
        <tr>
            <td>supportingInfo</td>
            <td></td>
            <td></td>
            <td></td>
            <td><a href="https://hl7.org/fhir/R4/references.html#2.3.0">Reference</a></td>
            <td>Currently out of scope - element <b>SHALL NOT</b> be populated.</td>
        </tr>
        <tr>
            <td>bodySite</td>
            <td></td>
            <td></td>
            <td></td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#CodeableConcept">CodeableConcept</a></td>
            <td>Currently out of scope - element <b>SHALL NOT</b> be populated.</td>
        </tr>
        <tr>
            <td>patientInstruction</td>
            <td></td>
            <td></td>
            <td></td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#string">string</a></td>
            <td>Currently out of scope - element <b>SHALL NOT</b> be populated.</td>
        </tr>
        <tr>
            <td>relevantHistory</td>
            <td></td>
            <td></td>
            <td></td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#CodeableConcept">CodeableConcept</a></td>
            <td>Currently out of scope - element <b>SHALL NOT</b> be populated.</td>
        </tr>
    </tbody>
</table>

<br>