---
topic: R4Practitioner
---
## Profile: UKCore-Practitioner

### Summary
Used to represent the following (where applicable):
* the person that requested a pathology test e.g. a GP
* the person that performed a pathology test e.g. a biomedical scientist
* the person that produced a pathology test report e.g. a consultant chemical pathologist
* the person that collected a specimen e.g. a phlebotomist

### Resource and Profile Links
* R4 Resource (Base): [Practitioner](https://hl7.org/fhir/R4/practitioner.html)
* R4 UK Core Profile: [UKCore-Practitioner](https://simplifier.net/guide/uk-core-implementation-guide-stu2/home/profilesandextensions/profile-ukcore-practitioner?current)

### Profile Views
Refer to {{pagelink:ProfileDescriptions}} for a definition of the different profile view formats.
<div class="tab fhirTree">
    <button class="tablinks active" onclick="openTab(event, 'Snapshot View')">Snapshot View</button>
    <button class="tablinks" onclick="openTab(event, 'Differential View')">Differential View</button>
    <button class="tablinks" onclick="openTab(event, 'Hybrid View')">Hybrid View</button>
</div>

<div id="Snapshot View" class="tabcontent" style="display:block">
    <h4>Snapshot View</h4>
    {{tree: https://fhir.hl7.org.uk/StructureDefinition/UKCore-Practitioner, snapshot}}
</div>

<div id="Differential View" class="tabcontent">
    <h4>Differential View</h4>
    {{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Practitioner, diff}}
</div>

<div id="Hybrid View" class="tabcontent">
    <h4>Hybrid View</h4>
    {{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Practitioner, hybrid}}
</div>

### Additional Guidance
The following table includes additional guidance that should be followed when implementing the `UKCore-Practitioner` profile. It should be used in conjunction with the profile definition included above. Refer to {{pagelink:ProfileDescriptions}} for a definition of the table column headings.

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
            <td>The canonical URL for the <code>UKCore-Practitioner</code> profile.<br><br>This <b>SHALL</b> be populated with the following fixed value:<br><code>https://fhir.hl7.org.uk/StructureDefinition/UKCore-Practitioner</code></td>
        </tr>
        <tr>
            <td>identifier</td>
            <td>0..*</td>
            <td><code>1..1</code></td>
            <td>Mandatory</td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#Identifier">Identifier</a></td>
            <td>The SDS User ID of the practitioner <b>SHALL</b> be used to populate the <code>sdsUserID</code> slice of the <code>identifier</code> element.</td>
        </tr>
        <tr>
            <td>active</td>
            <td>0..1</td>
            <td>0..1</td>
            <td>Optional</td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#boolean">boolean</a></td>
            <td></td>
        </tr>
        <tr>
            <td>name</td>
            <td>0..*</td>
            <td><code>1..1</code></td>
            <td>Required</td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#HumanName">HumanName</a></td>
            <td>The name of the practitioner <b>SHALL</b> be populated.</td>
        </tr>
        <tr>
            <td>telecom</td>
            <td>0..*</td>
            <td>0..*</td>
            <td>Optional</td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#ContactPoint">ContactPoint</a></td>
            <td></td>
        </tr>
        <tr>
            <td>address</td>
            <td>0..*</td>
            <td>0..*</td>
            <td>Optional</td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#Address">Address</a></td>
            <td></td>
        </tr>
        <tr>
            <td>gender</td>
            <td>0..1</td>
            <td>0..1</td>
            <td>Optional</td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#code">code</a></td>
            <td></td>
        </tr>
        <tr>
            <td>birthDate</td>
            <td>0..1</td>
            <td>0..1</td>
            <td>Optional</td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#date">date</a></td>
            <td></td>
        </tr>
        <tr>
            <td>photo</td>
            <td>0..*</td>
            <td>0..*</td>
            <td>Optional</td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#Attachment">Attachment</a></td>
            <td></td>
        </tr>
        <tr>
            <td>qualification</td>
            <td>0..*</td>
            <td>0..*</td>
            <td>Optional</td>
            <td><a href="https://hl7.org/fhir/R4/backboneelement.html">BackboneElement</a></td>
            <td></td>
        </tr>
        <tr>
            <td>communication</td>
            <td>0..*</td>
            <td>0..*</td>
            <td>Optional</td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#CodeableConcept">CodeableConcept</a></td>
            <td></td>
        </tr>
    </tbody>
</table>

<br>