---
topic: STU3Organization
---
## STU3 Profile: CareConnect-Organization-1

### Summary
Used to represent the following (where applicable):
* the organisation that requested a pathology test e.g. a GP practice
* the organisation that performed a pathology test e.g. a pathology laboratory
* the organisation that produced a pathology test report e.g. a pathology laboratory

### Related Links
* STU3 Resource: [Organization](http://hl7.org/fhir/STU3/organization.html)<br>
* STU3 CareConnect Profile: [CareConnect-Organization-1](https://simplifier.net/HL7FHIRCareConnectBaselineforSTU3/CareConnect-Organization-1)

### Profile Views
Refer to {{pagelink:ProfileDescriptions}} for a definition of the different profile view formats.
<div class="tab fhirTree">
    <button class="tablinks active" onclick="openTab(event, 'Snapshot View')">Snapshot View</button>
    <button class="tablinks" onclick="openTab(event, 'Differential View')">Differential View</button>
    <button class="tablinks" onclick="openTab(event, 'Hybrid View')">Hybrid View</button>
</div>

<div id="Snapshot View" class="tabcontent" style="display:block">
    <h4>Snapshot View</h4>
    {{tree:https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Organization-1, snapshot}}
</div>

<div id="Differential View" class="tabcontent">
    <h4>Differential View</h4>
    {{tree:https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Organization-1, diff}}
</div>

<div id="Hybrid View" class="tabcontent">
    <h4>Hybrid View</h4>
    {{tree:https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Organization-1, hybrid}}
</div>

### Conformance Rules
The following table describes additional conformance rules and constraints that should be applied when implementing the `CareConnect-Organization-1` profile as part of this specification. It should be used in conjunction with the profile definition included above. Refer to {{pagelink:ProfileDescriptions}} for a definition of the table column headings.

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
            <td><a href="http://hl7.org/fhir/stu3/datatypes.html#id">id</a></td>
            <td>The logical identifier for the resource instance.</td>
        </tr>
        <tr>
            <td>meta.profile</td>
            <td>0..*</td>
            <td><code>1..1</code></td>
            <td>Mandatory</td>
            <td><a href="http://hl7.org/fhir/stu3/datatypes.html#uri">uri</a></td>
            <td>The URL for the <code>CareConnect-Organization-1</code> profile.<br><br>This <b>SHALL</b> be populated with the following fixed value:<br><code>https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Organization-1</code></td>
        </tr>
        <tr>
            <td>extension (mainLocation)</td>
            <td>0..1</td>
            <td>0..1</td>
            <td>Optional</td>
            <td><a href="http://hl7.org/fhir/stu3/extensibility.html#Extension">Extension</a></td>
            <td></td>
        </tr>
        <tr>
            <td>extension (organization-period)</td>
            <td>0..1</td>
            <td>0..1</td>
            <td>Optional</td>
            <td><a href="http://hl7.org/fhir/stu3/extensibility.html#Extension">Extension</a></td>
            <td></td>
        </tr>
        <tr>
            <td>identifier</td>
            <td>0..*</td>
            <td><code>1..1</code></td>
            <td>Mandatory</td>
            <td><a href="http://hl7.org/fhir/stu3/datatypes.html#Identifier">Identifier</a></td>
            <td>The ODS Organisation Code for the organisation <b>SHALL</b> be used to populate the <code>odsOrganisationCode</code> slice of the <code>identifier</code> element.</td>
        </tr>
        <tr>
            <td>active</td>
            <td>0..1</td>
            <td>0..1</td>
            <td>Required</td>
            <td><a href="http://hl7.org/fhir/stu3/datatypes.html#boolean">boolean</a></td>
            <td></td>
        </tr>
        <tr>
            <td>type</td>
            <td>0..*</td>
            <td>0..*</td>
            <td>Required</td>
            <td><a href="http://hl7.org/fhir/stu3/datatypes.html#CodeableConcept">CodeableConcept</a></td>
            <td></td>
        </tr>
        <tr>
            <td>name</td>
            <td>0..1</td>
            <td><code>1..1</code></td>
            <td>Required</td>
            <td><a href="http://hl7.org/fhir/stu3/datatypes.html#string">string</a></td>
            <td>The name of the organisation <b>SHALL</b> be populated.</td>
        </tr>
        <tr>
            <td>alias</td>
            <td>0..*</td>
            <td>0..*</td>
            <td>Optional</td>
            <td><a href="http://hl7.org/fhir/stu3/datatypes.html#string">string</a></td>
            <td></td>
        </tr>
        <tr>
            <td>telecom</td>
            <td>0..*</td>
            <td>0..*</td>
            <td>Optional</td>
            <td><a href="http://hl7.org/fhir/stu3/datatypes.html#ContactPoint">ContactPoint</a></td>
            <td></td>
        </tr>
        <tr>
            <td>address</td>
            <td>0..*</td>
            <td>0..*</td>
            <td>Optional</td>
            <td><a href="http://hl7.org/fhir/stu3/datatypes.html#Address">Address</a></td>
            <td></td>
        </tr>
        <tr>
            <td>partOf</td>
            <td>0..1</td>
            <td>0..1</td>
            <td>Optional</td>
            <td><a href="http://hl7.org/fhir/stu3/references.html#2.3.0">Reference</a></td>
            <td></td>
        </tr>
        <tr>
            <td>contact</td>
            <td>0..*</td>
            <td>0..*</td>
            <td>Optional</td>
            <td><a href="http://hl7.org/fhir/stu3/backboneelement.html">BackboneElement</a></td>
            <td></td>
        </tr>
        <tr>
            <td>endpoint</td>
            <td>0..*</td>
            <td>0..*</td>
            <td>Optional</td>
            <td><a href="http://hl7.org/fhir/stu3/references.html#2.3.0">Reference</a></td>
            <td></td>
        </tr>
    </tbody>
</table>

<br>