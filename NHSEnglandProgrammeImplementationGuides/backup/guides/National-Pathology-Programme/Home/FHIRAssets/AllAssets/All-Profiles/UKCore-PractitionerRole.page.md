---
topic: R4PractitionerRole
---
## Profile: UKCore-PractitionerRole

### Summary
Used to represent a specific set of roles/locations/specialties/services that a <code>Practitioner</code> may perform at an <code>Organization</code>.

### Resource and Profile Links
* R4 Resource (Base): [PractitionerRole](https://hl7.org/fhir/R4/practitionerrole.html)
* R4 UK Core Profile: [UKCore-PractitionerRole](https://simplifier.net/hl7fhirukcorer4/ukcore-practitionerrole)

### Profile Views
Refer to {{pagelink:ProfileDescriptions}} for a definition of the different profile view formats.
<div class="tab fhirTree">
    <button class="tablinks active" onclick="openTab(event, 'Snapshot View')">Snapshot View</button>
    <button class="tablinks" onclick="openTab(event, 'Differential View')">Differential View</button>
    <button class="tablinks" onclick="openTab(event, 'Hybrid View')">Hybrid View</button>
</div>

<div id="Snapshot View" class="tabcontent" style="display:block">
    <h4>Snapshot View</h4>
    {{tree: https://fhir.hl7.org.uk/StructureDefinition/UKCore-PractitionerRole, snapshot}}
</div>

<div id="Differential View" class="tabcontent">
    <h4>Differential View</h4>
    {{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-PractitionerRole, diff}}
</div>

<div id="Hybrid View" class="tabcontent">
    <h4>Hybrid View</h4>
    {{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-PractitionerRole, hybrid}}
</div>

### Additional Guidance
The following table includes additional guidance that should be followed when implementing the `UKCore-PractitionerRole` profile. It should be used in conjunction with the profile definition included above. Refer to {{pagelink:ProfileDescriptions}} for a definition of the table column headings. 

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
            <td>The canonical URL for the <code>UKCore-PractitionerRole</code> profile.<br><br>This <b>SHALL</b> be populated with the following fixed value:<br><code>https://fhir.hl7.org.uk/StructureDefinition/UKCore-PractitionerRole</code></td>
        </tr>
        <tr>
            <td>identifier</td>
            <td>0..*</td>
            <td><code>1..1</code></td>
            <td>Mandatory</td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#Identifier">Identifier</a></td>
            <td></td>
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
            <td>period</td>
            <td>0..1</td>
            <td>0..1</td>
            <td>Optional</td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#Period">Period</a></td>
            <td></td>
        </tr>
        <tr>
            <td>practitioner</td>
            <td>0..1</td>
            <td>0..1</td>
            <td>Optional</td>
            <td><a href="https://hl7.org/fhir/R4/references.html#2.3.0">Reference</a></td>
            <td></td>
        </tr>
        <tr>
            <td>organization</td>
            <td>0..1</td>
            <td>0..1</td>
            <td>Optional</td>
            <td><a href="https://hl7.org/fhir/R4/references.html#2.3.0">Reference</a></td>
            <td></td>
        </tr>
        <tr>
            <td>code</td>
            <td>0..*</td>
            <td>0..*</td>
            <td>Optional</td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#CodeableConcept">CodeableConcept</a></td>
            <td></td>
        </tr>
        <tr>
            <td>specialty</td>
            <td>0..*</td>
            <td>0..*</td>
            <td>Optional</td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#CodeableConcept">CodeableConcept</a></td>
            <td></td>
        </tr>
        <tr>
            <td>location</td>
            <td>0..*</td>
            <td>0..*</td>
            <td>Optional</td>
            <td><a href="https://hl7.org/fhir/R4/references.html#2.3.0">Reference</a></td>
            <td></td>
        </tr>
        <tr>
            <td>healthcareService</td>
            <td>0..*</td>
            <td>0..*</td>
            <td>Optional</td>
            <td><a href="https://hl7.org/fhir/R4/references.html#2.3.0">Reference</a></td>
            <td></td>
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
            <td>availableTime</td>
            <td>0..*</td>
            <td>0..*</td>
            <td>Optional</td>
            <td><a href="https://hl7.org/fhir/R4/backboneelement.html">BackboneElement</a></td>
            <td></td>
        </tr>
        <tr>
            <td>notAvailable</td>
            <td>0..*</td>
            <td>0..*</td>
            <td>Optional</td>
            <td><a href="https://hl7.org/fhir/R4/backboneelement.html">BackboneElement</a></td>
            <td></td>
        </tr
        <tr>
            <td>availabilityExceptions</td>
            <td>0..1</td>
            <td>0..1</td>
            <td>Optional</td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#string">string</a></td>
            <td></td>
        </tr>
        <tr>
            <td>endpoint</td>
            <td>0..*</td>
            <td>0..*</td>
            <td>Optional</td>
            <td><a href="https://hl7.org/fhir/R4/references.html#2.3.0">Reference</a></td>
            <td></td>
        </tr>
    </tbody>
</table>

<br>