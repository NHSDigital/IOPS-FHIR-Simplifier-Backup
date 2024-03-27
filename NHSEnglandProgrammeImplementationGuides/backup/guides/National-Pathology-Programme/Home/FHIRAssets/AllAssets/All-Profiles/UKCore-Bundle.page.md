---
topic: R4Bundle
---
## Profile: UKCore-Bundle

### Summary
A container for a collection of resources. Used to group the set of resources that comprise a pathology related message.

### Resource and Profile Links
* R4 Resource (Base): [Bundle](https://hl7.org/FHIR/R4/bundle.html)
* R4 UK Core Profile: [UKCore-Bundle](https://simplifier.net/hl7fhirukcorer4/ukcore-bundle)

### Profile Views
Refer to {{pagelink:ProfileDescriptions}} for a definition of the different profile view formats.
<div class="tab fhirTree">
<button class="tablinks active" onclick="openTab(event, 'Snapshot View')">Snapshot View</button>
<button class="tablinks" onclick="openTab(event, 'Differential View')">Differential View</button>
<button class="tablinks" onclick="openTab(event, 'Hybrid View')">Hybrid View</button>
</div>

<div id="Snapshot View" class="tabcontent" style="display:block">
<h4>Snapshot View</h4>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Bundle, snapshot}}
</div>

<div id="Differential View" class="tabcontent">
<h4>Differential View</h4>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Bundle, diff}}
</div>

<div id="Hybrid View" class="tabcontent">
<h4>Hybrid View</h4>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Bundle, hybrid}}
</div>

### Additional Guidance
The following table includes additional guidance that should be followed when implementing the `UKCore-Bundle` profile. It should be used in conjunction with the profile definition included above. Refer to {{pagelink:ProfileDescriptions}} for a definition of the table column headings.

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
            <td><a href="https://hl7.org/FHIR/R4/datatypes.html#id">id</a></td>
            <td>The logical identifier for the resource instance.</td>
        </tr>
        <tr>
            <td>meta.profile</td>
            <td>0..*</td>
            <td><code>1..1</code></td>
            <td>Mandatory</td>
            <td><a href="https://hl7.org/FHIR/R4/datatypes.html#uri">uri</a></td>
            <td>The canonical URL for the <code>UKCore-Bundle</code> profile.<br><br>This <b>SHALL</b> be populated with the following fixed value:<br><code>https://fhir.hl7.org.uk/StructureDefinition/UKCore-Bundle</code></td>
        </tr>
            <td>identifier</td>
            <td>0..1</td>
            <td>0..1</td>
            <td>Optional</td>
            <td><a href="https://hl7.org/FHIR/R4/datatypes.html#Identifier">Identifier</a></td>
            <td>This <b>SHALL</b> be populated with a globally unique and persistent identifier (that is, it doesn’t change between requests and is therefore stored with the source data). This <b>SHALL</b> be scoped by a provider specific namespace for the identifier.<br><br>Where consuming systems are integrating data from this resource to their local system, they <b>SHALL</b> also persist this identifier at the same time</td>
        </tr>
        <tr>
            <td>type</td>
            <td>1..1</td>
            <td>1..1</td>
            <td>Mandatory</td>
            <td><a href="https://hl7.org/FHIR/R4/datatypes.html#code">code</a></td>
            <td>This <b>SHALL</b> be populated with a fixed value of <code>message</code>.</td>
        </tr>
        <tr>
            <td>timestamp</td>
            <td>0..1</td>
            <td>0..1</td>
            <td>Optional</td>
            <td><a href="https://hl7.org/FHIR/R4/datatypes.html#instant">instant</a></td>
            <td></td>
        </tr>
        <tr>
            <td>total</td>
            <td>0..1</td>
            <td>0..1</td>
            <td>Optional</td>
            <td><a href="https://hl7.org/FHIR/R4/datatypes.html#unsignedInt">unsignedInt</a></td>
            <td></td>
        </tr>
        <tr>
            <td>link</td>
            <td>0..*</td>
            <td>0..*</td>
            <td>Optional</td>
            <td><a href="https://hl7.org/FHIR/R4/backboneelement.html">BackboneElement</a></td>
            <td></td>
        </tr>
        <tr>
            <td>entry</td>
            <td>0..*</td>
            <td>0..*</td>
            <td>Optional</td>
            <td><a href="https://hl7.org/FHIR/R4/backboneelement.html">BackboneElement</a></td>
            <td>References to the resources that are included in the <code>Bundle</code>. Refer to the following for details:
                <ul>
                    <li>{{pagelink:BuildContructPathologyRequestBundle}}</li>
                    <li>{{pagelink:BuildContructPathologyReportBundle}}</li>
                </ul>
            </td>
        </tr>
        <tr>
            <td>signature</td>
            <td>0..1</td>
            <td>0..1</td>
            <td>Optional</td>
            <td><a href="https://hl7.org/FHIR/R4/datatypes.html#Signature">Signature</a></td>
            <td></td>
        </tr>
    </tbody>
</table>

<br>