---
topic: R4Organization
---
## Profile: UKCore-Organization

### Summary
Used to represent the following (where applicable):
* the organisation that requested a pathology test e.g. a GP practice
* the organisation that performed a pathology test e.g. a pathology laboratory
* the organisation that produced a pathology test report e.g. a pathology laboratory

### Resource and Profile Links
* R4 Resource (Base): [Organization]( https://hl7.org/fhir/R4/organization.html)
* R4 UK Core Profile: [UKCore-Organization](https://simplifier.net/hl7fhirukcorer4/ukcore-organization)

### Profile Views
Refer to {{pagelink:ProfileDescriptions}} for a definition of the different profile view formats.
<div class="tab fhirTree">
    <button class="tablinks active" onclick="openTab(event, 'Snapshot View')">Snapshot View</button>
    <button class="tablinks" onclick="openTab(event, 'Differential View')">Differential View</button>
    <button class="tablinks" onclick="openTab(event, 'Hybrid View')">Hybrid View</button>
</div>

<div id="Snapshot View" class="tabcontent" style="display:block">
    <h4>Snapshot View</h4>
    {{tree: https://fhir.hl7.org.uk/StructureDefinition/UKCore-Organization, snapshot}}
</div>

<div id="Differential View" class="tabcontent">
    <h4>Differential View</h4>
    {{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Organization, diff}}
</div>

<div id="Hybrid View" class="tabcontent">
    <h4>Hybrid View</h4>
    {{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Organization, hybrid}}
</div>

### Additional Guidance
The following table includes additional guidance that should be followed when implementing the `UKCore-Organization` profile. It should be used in conjunction with the profile definition included above. Refer to {{pagelink:ProfileDescriptions}} for a definition of the table column headings.

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
            <td>The canonical URL for the <code>UKCore-Organization</code> profile.<br><br>This <b>SHALL</b> be populated with the following fixed value:<br><code>https://fhir.hl7.org.uk/StructureDefinition/UKCore-Organization</code></td>
        </tr>
        <tr>
            <td>extension (mainLocation)</td>
            <td>0..*</td>
            <td>0..*</td>
            <td>Optional</td>
            <td><a href=" https://hl7.org/fhir/R4/extensibility.html#Extension">Extension</a></td>
            <td></td>
        </tr>
        <tr>
            <td>extension (organization-period)</td>
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
            <td>The ODS Organisation Code for the organisation <b>SHALL</b> be used to populate the <code>odsOrganisationCode</code> slice of the <code>identifier</code> element.</td>
        </tr>
        <tr>
            <td>active</td>
            <td>0..1</td>
            <td>0..1</td>
            <td>Required</td>
            <td><a href=" https://hl7.org/fhir/R4/datatypes.html#boolean">boolean</a></td>
            <td></td>
        </tr>
        <tr>
            <td>type</td>
            <td>0..*</td>
            <td>0..*</td>
            <td>Required</td>
            <td><a href=" https://hl7.org/fhir/R4/datatypes.html#CodeableConcept">CodeableConcept</a></td>
            <td></td>
        </tr>
        <tr>
            <td>name</td>
            <td>0..1</td>
            <td><code>1..1</code></td>
            <td>Required</td>
            <td><a href=" https://hl7.org/fhir/R4/datatypes.html#string">string</a></td>
            <td>The name of the organisation <b>SHALL</b> be populated.</td>
        </tr>
        <tr>
            <td>alias</td>
            <td>0..*</td>
            <td>0..*</td>
            <td>Optional</td>
            <td><a href=" https://hl7.org/fhir/R4/datatypes.html#string">string</a></td>
            <td></td>
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
            <td>address</td>
            <td>0..*</td>
            <td>0..*</td>
            <td>Optional</td>
            <td><a href=" https://hl7.org/fhir/R4/datatypes.html#Address">Address</a></td>
            <td></td>
        </tr>
        <tr>
            <td>partOf</td>
            <td>0..1</td>
            <td>0..1</td>
            <td>Optional</td>
            <td><a href=" https://hl7.org/fhir/R4/references.html#2.3.0">Reference</a></td>
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
            <td>endpoint</td>
            <td>0..*</td>
            <td>0..*</td>
            <td>Optional</td>
            <td><a href=" https://hl7.org/fhir/R4/references.html#2.3.0">Reference</a></td>
            <td></td>
        </tr>
    </tbody>
</table>

<br>