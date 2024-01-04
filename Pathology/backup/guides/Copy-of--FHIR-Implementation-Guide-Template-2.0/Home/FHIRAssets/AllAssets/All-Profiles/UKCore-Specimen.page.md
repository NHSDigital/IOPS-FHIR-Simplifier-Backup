---
topic: R4Specimen
---
## R4 Profile: UKCore-Specimen

### Summary
Details of the specimen(s) provided for testing.

### Resource and Profile Links
* R4 Resource (Base): [Specimen]( https://hl7.org/fhir/R4/specimen.html)
* R4 UK Core Profile: [UKCore-Specimen](https://simplifier.net/hl7fhirukcorer4/ukcore-specimen)

### Profile Views
Refer to {{pagelink:ProfileDescriptions}} for a definition of the different profile view formats.
<div class="tab fhirTree">
    <button class="tablinks active" onclick="openTab(event, 'Snapshot View')">Snapshot View</button>
    <button class="tablinks" onclick="openTab(event, 'Differential View')">Differential View</button>
    <button class="tablinks" onclick="openTab(event, 'Hybrid View')">Hybrid View</button>
</div>

<div id="Snapshot View" class="tabcontent" style="display:block">
    <h4>Snapshot View</h4>
    {{tree: https://fhir.hl7.org.uk/StructureDefinition/UKCore-Specimen, snapshot}}
</div>

<div id="Differential View" class="tabcontent">
    <h4>Differential View</h4>
    {{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Specimen, diff}}
</div>

<div id="Hybrid View" class="tabcontent">
    <h4>Hybrid View</h4>
    {{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Specimen, hybrid}}
</div>

### Additional Guidance
The following table includes additional guidance that should be followed when implementing the `UKCore-Specimen` profile. It should be used in conjunction with the profile definition included above. Refer to {{pagelink:ProfileDescriptions}} for a definition of the table column headings.

An example of how each supported data element may be populated is provided in {{pagelink:R4SnippetsSpecimen}}.

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
            <td>The canonical URL for the <code>UKCore-Specimen</code> profile.<br><br>This <b>SHALL</b> be populated with the following fixed value:<br><code>https://fhir.hl7.org.uk/StructureDefinition/UKCore-Specimen</code></td>
        </tr>
        <tr>
            <td>identifier</td>
            <td>0..*</td>
            <td><code>1..*</code></td>
            <td>Mandatory</td>
            <td><a href=" https://hl7.org/fhir/R4/datatypes.html#Identifier">Identifier</a></td>
            <td>This <b>SHALL</b> be populated with a globally unique and persistent identifier (that is, it doesn’t change between requests and is therefore stored with the source data). This <b>SHALL</b> be scoped by a provider specific namespace for the identifier.<br><br>Where consuming systems are integrating data from this resource to their local system, they <b>SHALL</b> also persist this identifier at the same time.</td>
        </tr>
        <tr>
            <td>accessionIdentifier</td>
            <td>0..1</td>
            <td>0..1</td>
            <td>Required</td>
            <td><a href=" https://hl7.org/fhir/R4/datatypes.html#Identifier">Identifier</a></td>
            <td>A business identifier supplied by the laboratory that is responsible for performing the test.</td>
        </tr>
        <tr>
            <td>status</td>
            <td>0..1</td>
            <td>0..1</td>
            <td>Required</td>
            <td><a href=" https://hl7.org/fhir/R4/datatypes.html#code">code</a></td>
            <td>The availability of the specimen.</td>
        </tr>
        <tr>
            <td>type</td>
            <td>0..1</td>
            <td>0..1</td>
            <td>Required</td>
            <td><a href=" https://hl7.org/fhir/R4/datatypes.html#CodeableConcept">CodeableConcept</a></td>
            <td>The kind of material that forms the specimen.<br><br>If provided, this <b>SHALL</b> be populated using one of the following:<br><br>
                <ul>
                    <li>descendantOf 105590001 | Substance (in which case <code>Specimen.collection.method</code> and <code>Specimen.collection.bodySite</code> <b>SHOULD</b> also be populated), OR</li>
        			<li>descendantOf 49755003 | Morphologically abnormal structure, OR</li>
                    <li>descendantOf 123037004 | Body structure, OR</li>
                    <li>descendantOf 123038009 | Specimen, OR</li>
                    <li>descendantOf 260787004 | Physical object</li>
                </ul>
            </td>
        </tr>
        <tr>
            <td>subject</td>
            <td>0..1</td>
            <td><code>1..1</code></td>
            <td>Mandatory</td>
            <td><a href=" https://hl7.org/fhir/R4/references.html#2.3.0">Reference</a></td>
            <td>Reference to the subject that the specimen relates to. This is usually (but not always) a <code>Patient</code>.</td>
        </tr>
        <tr>
            <td>receivedTime</td>
            <td>0..1</td>
            <td>0..1</td>
            <td>Required</td>
            <td><a href=" https://hl7.org/fhir/R4/datatypes.html#datetime">datetime</a></td>
            <td>The date and time that the specimen was received for processing.</td>
        </tr>
        <tr>
            <td>request</td>
            <td>0..*</td>
            <td>0..*</td>
            <td>Required</td>
            <td><a href=" https://hl7.org/fhir/R4/references.html#2.3.0">Reference</a></td>
            <td>Reference to the <code>ServiceRequest</code> that the specimen relates to. This should only be used when a test was requested before the specimen was collected.<br><br><b>Note:</b> It is also possible to link a <code>ServiceRequest</code> to a <code>Specimen</code> using the <code>ServiceRequest.specimen</code> data element. This should be used when a test is requested and the specimen has already been collected.<br><br>For further information refer to:<br><br> 
                <ul>
                    <li>the description of the {{pagelink:R4ServiceRequest}} profile in this implementation guide, and</li>
                    <li>the notes relating to the use of the<a href=" https://hl7.org/fhir/R4/servicerequest.html#notes"> ServiceRequest</a> resource in the base FHIR specification.</li>
                </ul>
            </td>
        </tr>
        <tr>
            <td>collection</td>
            <td>0..1</td>
            <td>0..1</td>
            <td>Required</td>
            <td><a href=" https://hl7.org/fhir/R4/backboneelement.html">BackboneElement</a></td>
            <td>Details concerning the specimen collection.</td>
        </tr>
        <tr>
            <td>collection.collector</td>
            <td>0..1</td>
            <td>0..1</td>
            <td>Required</td>
            <td><a href=" https://hl7.org/fhir/R4/references.html#2.3.0">Reference</a></td>
            <td>Reference to the <code>Practitioner</code> or <code>PractitionerRole</code> that collected the specimen.</td>
        </tr>
        <tr>
            <td>collection.collected[x]</td>
            <td>0..1</td>
            <td>0..1</td>
            <td>Required</td>
            <td><a href=" https://hl7.org/fhir/R4/datatypes.html#dateTime">dateTime</a> | <a href=" https://hl7.org/fhir/R4/datatypes.html#Period">Period</a></td>
            <td>The date and time that the specimen was collected.<br><br>The presence of <code>[x]</code> in an element name is used to indicate a <a href="https://hl7.org/fhir/R4/formats.html#choice"> choice of data type</a>. The <code>[x]</code> part of the element name is replaced with an appropriate data type, in title-case format e.g. <code>effectiveDateTime</code>.</td>
        </tr>
        <tr>
            <td>collection.quantity</td>
            <td>0..1</td>
            <td>0..1</td>
            <td>Required</td>
            <td><a href=" https://hl7.org/fhir/R4/datatypes.html#SimpleQuantity">SimpleQuantity</a></td>
            <td>The quantity of specimen that was collected.</td>
        </tr>
        <tr>
            <td>collection.bodySite</td>
            <td>0..1</td>
            <td>0..1</td>
            <td>Required</td>
            <td><a href=" https://hl7.org/fhir/R4/datatypes.html#CodeableConcept">CodeableConcept</a></td>
            <td>The anatomical site of the specimen collection.</td>
        </tr>
            <tr>
            <td>collection.fastingStatus[x]</td>
            <td>0..1</td>
            <td>0..1</td>
            <td>Required</td>
            <td><a href=" https://hl7.org/fhir/R4/datatypes.html#CodeableConcept">CodeableConcept</a> | <a href=" https://hl7.org/fhir/R4/datatypes.html#Duration">Duration</a></td>
            <td>Indicates abstinence or reduction from some or all food, drink, or both, for a period of time prior to specimen collection<br><br>The presence of <code>[x]</code> in an element name is used to indicate a <a href="https://hl7.org/fhir/R4/formats.html#choice"> choice of data type</a>. The <code>[x]</code> part of the element name is replaced with an appropriate data type, in title-case format e.g. <code>fastingStatusCodeableConcept</code></td>
        </tr>
        <tr>
            <td>condition</td>
            <td>0..*</td>
            <td>0..*</td>
            <td>Required</td>
            <td><a href=" https://hl7.org/fhir/R4/datatypes.html#CodeableConcept">CodeableConcept</a></td>
        <td>The state of the specimen e.g. Contaminated.<br><br>It can be used to assess the availability, quality or appropriateness of the specimen for a specific test.</td>
        </tr>
        <tr>
            <td>note</td>
            <td>0..*</td>
            <td>0..*</td>
            <td>Required</td>
            <td><a href=" https://hl7.org/fhir/R4/datatypes.html#annotation">Annotation</a></td>
            <td>Notes relating to the specimen.</td>
        </tr>
        <tr>
            <td>parent</td>
            <td></td>
            <td></td>
            <td></td>
            <td><a href=" https://hl7.org/fhir/R4/references.html#2.3.0">Reference</a></td>
            <td>Currently out of scope - element <b>SHALL NOT</b> be populated.</td>
        </tr>
        <tr>
            <td>collection.duration</td>
            <td></td>
            <td></td>
            <td></td>
            <td><a href=" https://hl7.org/fhir/R4/datatypes.html#Duration">Duration</a></td>
            <td>Currently out of scope - element <b>SHALL NOT</b> be populated.</td>
        </tr>
        <tr>
            <td>collection.method</td>
            <td></td>
            <td></td>
            <td></td>
            <td><a href=" https://hl7.org/fhir/R4/datatypes.html#CodeableConcept">CodeableConcept</a></td>
            <td>Currently out of scope - element <b>SHALL NOT</b> be populated.</td>
        </tr>
        <tr>
            <td>processing</td>
            <td></td>
            <td></td>
            <td></td>
            <td><a href=" https://hl7.org/fhir/R4/backboneelement.html">BackboneElement</a></td>
            <td>Currently out of scope - element <b>SHALL NOT</b> be populated.</td>
        </tr>
        <tr>
            <td>processing.description</td>
            <td></td>
            <td></td>
            <td></td>
            <td><a href=" https://hl7.org/fhir/R4/datatypes.html#string">string</a></td>
            <td>Currently out of scope - element <b>SHALL NOT</b> be populated.</td>
        </tr>
        <tr>
            <td>processing.procedure</td>
            <td></td>
            <td></td>
            <td></td>
            <td><a href=" https://hl7.org/fhir/R4/datatypes.html#CodeableConcept">CodeableConcept</a></td>
            <td>Currently out of scope - element <b>SHALL NOT</b> be populated.</td>
        </tr>
        <tr>
            <td>processing.additive</td>
            <td></td>
            <td></td>
            <td></td>
            <td><a href=" https://hl7.org/fhir/R4/references.html#2.3.0">Reference</a></td>
            <td>Currently out of scope - element <b>SHALL NOT</b> be populated.</td>
        </tr>
        <tr>
            <td>processing.time[x]</td>
            <td></td>
            <td></td>
            <td></td>
            <td><a href=" https://hl7.org/fhir/R4/datatypes.html#dateTime">dateTime</a> | <a href=" https://hl7.org/fhir/R4/datatypes.html#Period">Period</a></td>
            <td>Currently out of scope - element <b>SHALL NOT</b> be populated.</td>
        </tr>
        <tr>
            <td>container</td>
            <td></td>
            <td></td>
            <td></td>
            <td><a href=" https://hl7.org/fhir/R4/backboneelement.html">BackboneElement</a></td>
            <td>Currently out of scope - element <b>SHALL NOT</b> be populated.</td>
        </tr>
        <tr>
            <td>container.identifier</td>
            <td></td>
            <td></td>
            <td></td>
            <td><a href=" https://hl7.org/fhir/R4/datatypes.html#Identifier">Identifier</a></td>
            <td>Currently out of scope - element <b>SHALL NOT</b> be populated.</td>
        </tr>
        <tr>
            <td>container.description</td>
            <td></td>
            <td></td>
            <td></td>
            <td><a href=" https://hl7.org/fhir/R4/datatypes.html#string">string</a></td>
            <td>Currently out of scope - element <b>SHALL NOT</b> be populated.</td>
        </tr>
        <tr>
            <td>container.type</td>
            <td></td>
            <td></td>
            <td></td>
            <td><a href=" https://hl7.org/fhir/R4/datatypes.html#CodeableConcept">CodeableConcept</a></td>
            <td>Currently out of scope - element <b>SHALL NOT</b> be populated.</td>
        </tr>
        <tr>
            <td>container.capacity</td>
            <td></td>
            <td></td>
            <td></td>
            <td><a href=" https://hl7.org/fhir/R4/datatypes.html#SimpleQuantity">SimpleQuantity</a></td>
            <td>Currently out of scope - element <b>SHALL NOT</b> be populated.</td>
        </tr>
        <tr>
            <td>container.specimenQuantity</td>
            <td></td>
            <td></td>
            <td></td>
            <td><a href=" https://hl7.org/fhir/R4/datatypes.html#SimpleQuantity">SimpleQuantity</a></td>
            <td>Currently out of scope - element <b>SHALL NOT</b> be populated.</td>
        </tr>
        <tr>
            <td>container.additive[x]</td>
            <td></td>
            <td></td>
            <td></td>
            <td><a href=" https://hl7.org/fhir/R4/datatypes.html#CodeableConcept">CodeableConcept</a> | <a href=" https://hl7.org/fhir/R4/references.html#2.3.0">Reference</a></td>
            <td>Currently out of scope - element <b>SHALL NOT</b> be populated.</td>
        </tr
    </tbody>
</table>

<br>
