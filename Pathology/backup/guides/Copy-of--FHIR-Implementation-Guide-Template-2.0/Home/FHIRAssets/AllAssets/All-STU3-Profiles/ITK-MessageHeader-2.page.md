---
topic: STU3MessageHeader
---
## STU3 Profile: ITK-MessageHeader-2

### Summary
The header for a message exchange that is either requesting or responding to an action.

### Related Links
* STU3 Resource: [MessageHeader](http://hl7.org/fhir/STU3/messageheader.html)
* STU3 ITK Profile: [ITK-Message-MessageHeader-2](https://fhir.nhs.uk/STU3/StructureDefinition/ITK-MessageHeader-2)

### Profile Views
Refer to {{pagelink:ProfileDescriptions}} for a definition of the different profile view formats.
<div class="tab fhirTree">
    <button class="tablinks active" onclick="openTab(event, 'Snapshot View')">Snapshot View</button>
    <button class="tablinks" onclick="openTab(event, 'Differential View')">Differential View</button>
    <button class="tablinks" onclick="openTab(event, 'Hybrid View')">Hybrid View</button>
</div>

<div id="Snapshot View" class="tabcontent" style="display:block">
    <h4>Snapshot View</h4>
    {{tree:https://fhir.nhs.uk/STU3/StructureDefinition/ITK-MessageHeader-2, snapshot}}
</div>

<div id="Differential View" class="tabcontent">
    <h4>Differential View</h4>
    {{tree:https://fhir.nhs.uk/STU3/StructureDefinition/ITK-MessageHeader-2, diff}}
</div>

<div id="Hybrid View" class="tabcontent">
    <h4>Hybrid View</h4>
    {{tree:https://fhir.nhs.uk/STU3/StructureDefinition/ITK-MessageHeader-2, hybrid}}
</div>

### Conformance Rules
The following table describes additional conformance rules and constraints that should be applied when implementing the `ITK-MessageHeader-2` profile as part of this specification. It should be used in conjunction with the profile definition included above. Refer to {{pagelink:ProfileDescriptions}} for a definition of the table column headings.

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
            <td>The canonical URL for the <code>ITK-MessageHeader-2</code> profile.<br><br>This <b>SHALL</b> be populated with the following fixed value:<br><code>https://fhir.nhs.uk/STU3/StructureDefinition/ITK-MessageHeader-2</code></td>
        </tr>
        <tr>
            <td>extension (ITKMessageHandling)</td>
            <td>1..1</td>
            <td>1..1</td>
            <td>Mandatory</td>
            <td><a href="http://hl7.org/fhir/stu3/extensibility.html#Extension">Extension</a></td>
            <td></td>
        </tr>
        <tr>
            <td>event</td>
            <td>1..1</td>
            <td>1..1</td>
            <td>Mandatory</td>
            <td><a href="http://hl7.org/fhir/stu3/datatypes.html#Coding">Coding</a></td>
            <td></td>
        </tr>
        <tr>
            <td>receiver</td>
            <td>0..1</td>
            <td>0..1</td>
            <td>Optional</td>
            <td><a href="http://hl7.org/fhir/stu3/references.html#2.3.0">Reference</a></td>
            <td></td>
        </tr>
        <tr>
            <td>sender</td>
            <td>1..1</td>
            <td>1..1</td>
            <td>Mandatory</td>
            <td><a href="http://hl7.org/fhir/stu3/references.html#2.3.0">Reference</a></td>
            <td></td>
        </tr>
        <tr>
            <td>timestamp</td>
            <td>1..1</td>
            <td>1..1</td>
            <td>Mandatory</td>
            <td><a href="http://hl7.org/fhir/stu3/datatypes.html#instant">instant</a></td>
            <td></td>
        </tr>
        <tr>
            <td>source</td>
            <td>1..1</td>
            <td>1..1</td>
            <td>Mandatory</td>
            <td><a href="http://hl7.org/fhir/stu3/backboneelement.html">BackboneElement</a></td>
            <td></td>
        </tr>
        <tr>
            <td>response</td>
            <td>0..1</td>
            <td>0..1</td>
            <td>Optional</td>
            <td><a href="http://hl7.org/fhir/stu3/backboneelement.html">BackboneElement</a></td>
            <td></td>
        </tr>
        <tr>
            <td>focus</td>
            <td>0..1</td>
            <td>0..1</td>
            <td>Optional</td>
            <td><a href="http://hl7.org/fhir/stu3/references.html#2.3.0">Reference</a></td>
            <td></td>
        </tr>
    </tbody>
</table>

<br>