---
topic: R4Patient
---
## Profile: UKCore-Patient

### Summary
Demographics and other administrative information about an individual. In most cases the subject of a pathology test request and/or test report is a `Patient` but it could be a `Group`, `Device` or `Location`.

### Resource and Profile Links
* R4 Resource (Base): [Patient]( https://hl7.org/fhir/R4/patient.html)
* R4 UK Core Profile: [UKCore-Patient](https://simplifier.net/hl7fhirukcorer4/ukcore-patient)

### Profile Views
Refer to {{pagelink:ProfileDescriptions}} for a definition of the different profile view formats.
<div class="tab fhirTree">
    <button class="tablinks active" onclick="openTab(event, 'Snapshot View')">Snapshot View</button>
    <button class="tablinks" onclick="openTab(event, 'Differential View')">Differential View</button>
    <button class="tablinks" onclick="openTab(event, 'Hybrid View')">Hybrid View</button>
</div>

<div id="Snapshot View" class="tabcontent" style="display:block">
    <h4>Snapshot View</h4>
    {{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Patient,snapshot}}
</div>

<div id="Differential View" class="tabcontent">
    <h4>Differential View</h4>
    {{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Patient, diff}}
</div>

<div id="Hybrid View" class="tabcontent">
    <h4>Hybrid View</h4>
    {{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Patient, hybrid}}
</div>

### Additional Guidance
The following table includes additional guidance that should be followed when implementing the `UKCore-Patient` profile. It should be used in conjunction with the profile definition included above. Refer to {{pagelink:ProfileDescriptions}} for a definition of the table column headings.

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
            <td><a href=" https://hl7.org/fhir/R4/datatypes.html#id">id</a></td>
            <td>The logical identifier for the resource instance.</td>
        </tr>
        <tr>
            <td>meta.profile</td>
            <td>0..*</td>
            <td><code>1..1</code></td>
            <td>Mandatory</td>
            <td><a href=" https://hl7.org/fhir/R4/datatypes.html#uri">uri</a></td>
            <td>The canonical URL for the <code>UKCore-Patient</code> profile.<br><br>This <b>SHALL</b> be populated with the following fixed value:<br><code>https://fhir.hl7.org.uk/StructureDefinition/UKCore-Patient</code></td>
        </tr>
        <tr>
            <td>extension (birthPlace)</td>
            <td>0..1</td>
            <td>0..1</td>
            <td>Optional</td>
            <td><a href=" https://hl7.org/fhir/R4/extensibility.html#Extension">Extension</a></td>
            <td></td>
        </tr>
        <tr>
            <td>extension (birthSex)</td>
            <td>0..1</td>
            <td>0..1</td>
            <td>Optional</td>
            <td><a href=" https://hl7.org/fhir/R4/extensibility.html#Extension">Extension</a></td>
            <td></td>
        </tr>
        <tr>
            <td>extension (cadavericDonor)</td>
            <td>0..1</td>
            <td>0..1</td>
            <td>Optional</td>
            <td><a href=" https://hl7.org/fhir/R4/extensibility.html#Extension">Extension</a></td>
            <td></td>
        </tr>
        <tr>
            <td>extension (contactPreference)</td>
            <td>0..1</td>
            <td>0..1</td>
            <td>Optional</td>
            <td><a href=" https://hl7.org/fhir/R4/extensibility.html#Extension">Extension</a></td>
            <td></td>
        </tr>
        <tr>
            <td>extension (deathNotificationStatus)</td>
            <td>0..1</td>
            <td>0..1</td>
            <td>Optional</td>
            <td><a href=" https://hl7.org/fhir/R4/extensibility.html#Extension">Extension</a></td>
            <td></td>
        </tr>
        <tr>
            <td>extension (ethnicCategory)</td>
            <td>0..1</td>
            <td>0..1</td>
            <td>Optional</td>
            <td><a href=" https://hl7.org/fhir/R4/extensibility.html#Extension">Extension</a></td>
            <td></td>
        </tr>
        <tr>
            <td>extension (residentialStatus)</td>
            <td>0..1</td>
            <td>0..1</td>
            <td>Optional</td>
            <td><a href=" https://hl7.org/fhir/R4/extensibility.html#Extension">Extension</a></td>
            <td></td>
        </tr>
        <tr>
            <td>extension (patientInterpreterRequired)</td>
            <td>0..1</td>
            <td>0..1</td>
            <td>Optional</td>
            <td><a href=" https://hl7.org/fhir/R4/extensibility.html#Extension">Extension</a></td>
            <td></td>
        </tr>
        <tr>
            <td>identifier</td>
            <td>0..*</td>
            <td><code>1..1</code></td>
            <td>Mandatory</td>
            <td><a href=" https://hl7.org/fhir/R4/datatypes.html#Identifier">Identifier</a></td>
            <td>The <code>identifier</code> element <b>SHALL</b> be populated using the Extension-UKCore-NHSNumberVerification element.<br><br><b>Note:</b> The <code>text</code> element has optional cardinality and does not need to be populated. The human-readable value for the NHS Number Verification Status provided is articulated within the <code>display</code> value within the <code>valueCodeableConcept</code> element.</td>
        </tr>
        <tr>
            <td>active</td>
            <td>0..1</td>
            <td>0..1</td>
            <td>Optional</td>
            <td><a href=" https://hl7.org/fhir/R4/datatypes.html#boolean">boolean</a></td>
            <td></td>
        </tr>
        <tr>
            <td>name</td>
            <td>0..*</td>
            <td><code>1..1</code></td>
            <td>Required</td>
            <td><a href=" https://hl7.org/fhir/R4/datatypes.html#HumanName">HumanName</a></td>
            <td>The name of the patient <b>SHALL</b> be populated.</td>
        </tr>
        <tr>
            <td>telecom</td>
            <td>0..*</td>
            <td>0..*</td>
            <td>Optional</td>
            <td><a href=" https://hl7.org/fhir/R4/datatypes.html#ContactPoint">ContactPoint</a></td>
            <td></td>
        </tr>
        <tr>
            <td>gender</td>
            <td>0..1</td>
            <td>0..1</td>
            <td>Optional</td>
            <td><a href=" https://hl7.org/fhir/R4/datatypes.html#code">code</a></td>
            <td></td>
        </tr>
        <tr>
            <td>birthDate</td>
            <td>0..1</td>
            <td>0..1</td>
            <td>Optional</td>
            <td><a href=" https://hl7.org/fhir/R4/datatypes.html#date">date</a></td>
            <td></td>
        </tr>
        <tr>
            <td>deceased[x]</td>
            <td>0..1</td>
            <td>0..1</td>
            <td>Optional</td>
            <td><a href=" https://hl7.org/fhir/R4/datatypes.html#boolean">boolean</a> | <a href=" https://hl7.org/fhir/R4/datatypes.html#dateTime">dateTime</a></td>
            <td></td>
        </tr>
        <tr>
            <td>address</td>
            <td>0..*</td>
            <td>0..*</td>
            <td>Optional</td>
            <td><a href=" https://hl7.org/fhir/R4/datatypes.html#Address">Address</a></td>
            <td></td>
        </tr>
        <tr>
            <td>maritalStatus</td>
            <td>0..1</td>
            <td>0..1</td>
            <td>Optional</td>
            <td><a href=" https://hl7.org/fhir/R4/datatypes.html#CodeableConcept">CodeableConcept</a></td>
            <td></td>
        </tr>
        <tr>
            <td>multipleBirth[x]</td>
            <td>0..1</td>
            <td>0..1</td>
            <td>Optional</td>
            <td><a href=" https://hl7.org/fhir/R4/datatypes.html#boolean">boolean</a> | <a href=" https://hl7.org/fhir/R4/datatypes.html#integer">integer</a></td>
            <td></td>
        </tr>
        <tr>
            <td>photo</td>
            <td>0..*</td>
            <td>0..*</td>
            <td>Optional</td>
            <td><a href=" https://hl7.org/fhir/R4/datatypes.html#Attachment">Attachment</a></td>
            <td></td>
        </tr>
        <tr>
            <td>contact</td>
            <td>0..*</td>
            <td>0..*</td>
            <td>Optional</td>
            <td><a href=" https://hl7.org/fhir/R4/backboneelement.html">BackboneElement</a></td>
            <td></td>
        </tr>
        <tr>
            <td>generalPractitioner</td>
            <td>0..*</td>
            <td>0..*</td>
            <td>Optional</td>
            <td><a href=" https://hl7.org/fhir/R4/references.html#2.3.0">Reference</a></td>
            <td></td>
        </tr>
        <tr>
            <td>managingOrganization</td>
            <td>0..1</td>
            <td>0..1</td>
            <td>Optional</td>
            <td><a href=" https://hl7.org/fhir/R4/references.html#2.3.0">Reference</a></td>
            <td></td>
        </tr>
        <tr>
            <td>link</td>
            <td>0..*</td>
            <td>0..*</td>
            <td>Optional</td>
            <td><a href=" https://hl7.org/fhir/R4/backboneelement.html">BackboneElement</a></td>
            <td></td>
        </tr>
    </tbody>
</table>

<br>