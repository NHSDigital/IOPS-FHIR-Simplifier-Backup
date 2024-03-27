---
topic: R4MessageHeader
---
## Profile: UKCore-MessageHeader

### Summary
The header for a message exchange that is either requesting or responding to an action.

### Resource and Profile Links
* R4 Resource (Base): [MessageHeader](https://hl7.org/fhir/R4/messageheader.html)
* R4 UK Core Profile: [UKCore-MessageHeader](https://simplifier.net/hl7fhirukcorer4/ukcore-messageheader)

### Profile Views
Refer to {{pagelink:ProfileDescriptions}} for a definition of the different profile view formats.
<div class="tab fhirTree">
    <button class="tablinks active" onclick="openTab(event, 'Snapshot View')">Snapshot View</button>
    <button class="tablinks" onclick="openTab(event, 'Differential View')">Differential View</button>
    <button class="tablinks" onclick="openTab(event, 'Hybrid View')">Hybrid View</button>
</div>

<div id="Snapshot View" class="tabcontent" style="display:block">
    <h4>Snapshot View</h4>
    {{tree: https://fhir.hl7.org.uk/StructureDefinition/UKCore-MessageHeader, snapshot}}
</div>

<div id="Differential View" class="tabcontent">
    <h4>Differential View</h4>
    {{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-MessageHeader, diff}}
</div>

<div id="Hybrid View" class="tabcontent">
    <h4>Hybrid View</h4>
    {{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-MessageHeader, hybrid}}
</div>

### Additional Guidance
The following table includes additional guidance that should be followed when implementing the `UKCore-MessageHeader`profile. It should be used in conjunction with the profile definition included above. Refer to {{pagelink:ProfileDescriptions}} for a definition of the table column headings.

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
            <td>The canonical URL for the <code>UKCore-MessageHeader</code> profile.<br><br>This <b>SHALL</b> be populated with the following fixed value:<br><code>https://fhir.hl7.org.uk/StructureDefinition/UKCore-MessageHeader</code></td>
        </tr>
        <tr>
            <td>extension (messageHeaderInstruction)</td>
            <td>0..*</td>
            <td>0..*</td>
            <td>Optional</td>
            <td><a href="https://hl7.org/fhir/R4/extensibility.html#Extension">Extension</a></td>
            <td></td>
        </tr>
        <tr>
            <td>event</td>
            <td>1..1</td>
            <td>1..1</td>
            <td>Mandatory</td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#Coding">Coding</a> | <a href="https://hl7.org/fhir/R4/datatypes.html#uri">uri</a></td>
            <td></td>
        </tr>
        <tr>
            <td>destination</td>
            <td>0..*</td>
            <td>0..*</td>
            <td>Optional</td>
            <td><a href="https://hl7.org/fhir/R4/backboneelement.html">BackboneElement</a></td>
            <td></td>
        </tr>
        <tr>
            <td>sender</td>
            <td>0..1</td>
            <td>0..1</td>
            <td>Optional</td>
            <td><a href="https://hl7.org/fhir/R4/references.html#2.3.0">Reference</a></td>
            <td></td>
        </tr>
        <tr>
            <td>enterer</td>
            <td>0..1</td>
            <td>0..1</td>
            <td>Optional</td>
            <td><a href="https://hl7.org/fhir/R4/references.html#2.3.0">Reference</a></td>
            <td></td>
        </tr>
        <tr>
            <td>author</td>
            <td>0..1</td>
            <td>0..1</td>
            <td>Optional</td>
            <td><a href="https://hl7.org/fhir/R4/references.html#2.3.0">Reference</a></td>
            <td></td>
        </tr>
        <tr>
            <td>destination</td>
            <td>0..*</td>
            <td>0..*</td>
            <td>Optional</td>
            <td><a href="https://hl7.org/fhir/R4/backboneelement.html">BackboneElement</a></td>
            <td></td>
        </tr>
        <tr>
            <td>timestamp</td>
            <td>1..1</td>
            <td>1..1</td>
            <td>Mandatory</td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#instant">instant</a></td>
            <td></td>
        </tr>
        <tr>
            <td>source</td>
            <td>1..1</td>
            <td>1..1</td>
            <td>Mandatory</td>
            <td><a href="https://hl7.org/fhir/R4/backboneelement.html">BackboneElement</a></td>
            <td></td>
        </tr>
        <tr>
            <td>responsible</td>
            <td>0..1</td>
            <td>0..1</td>
            <td>Optional</td>
            <td><a href="https://hl7.org/fhir/R4/references.html#2.3.0">Reference</a></td>
            <td></td>
        </tr>
        <tr>
            <td>reason</td>
            <td>0.1</td>
            <td>0..1</td>
            <td>Optional</td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#CodeableConcept">CodeableConcept</a></td>
            <td></td>
        </tr>
        <tr>
            <td>response</td>
            <td>0..1</td>
            <td>0..1</td>
            <td>Optional</td>
            <td><a href="https://hl7.org/fhir/R4/backboneelement.html">BackboneElement</a></td>
            <td></td>
        </tr>
        <tr>
            <td>focus</td>
            <td>0..*</td>
            <td>0..*</td>
            <td>Optional</td>
            <td><a href="https://hl7.org/fhir/R4/references.html#2.3.0">Reference</a></td>
            <td></td>
        </tr>
        <tr>
            <td>definition</td>
            <td>0..1</td>
            <td>0..1</td>
            <td>Optional</td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#canonical">canonical</a></td>
            <td></td>
        </tr>
    </tbody>
</table>

<br>