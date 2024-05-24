---
topic: R4Specimen
---
## UKCore-Specimen

### Summary
Details of the specimen(s) provided for testing.

### Resource and Profile Links
* R4 Resource (Base): [Specimen]( https://hl7.org/fhir/R4/specimen.html)
* R4 UK Core Profile: [UKCore-Specimen](https://simplifier.net/guide/uk-core-implementation-guide-stu2/home/profilesandextensions/profile-ukcore-specimen?current)

### Profile Views
Refer to {{pagelink:ProfileDescriptions}} for a definition of the different profile view formats.
<div class="tab fhirTree">
    <button class="tablinks active" onclick="openTab(event, 'Snapshot View')">Snapshot View</button>
    <button class="tablinks" onclick="openTab(event, 'Differential View')">Differential View</button>
    <button class="tablinks" onclick="openTab(event, 'Hybrid View')">Hybrid View</button>
    <button class="tablinks" onclick="openTab(event, 'Examples')">Examples</button>
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

<div id="Examples" class="tabcontent">
    <h4>Examples</h4>
    <b>UKCore-Specimen Snippets</b> - An example to illustrate how each supported data element in <code>UKCore-Specimen</code> may be populated.<br>{{pagelink:R4SnippetsSpecimen}}<br><br>
    <b>Bundle Examples</b> - Examples to illustrate the use of <code>UKCore-Specimen</code> within the context of a <code>Bundle</code>.<br>{{pagelink:R4BundleExampleHbA1cRequest}}<br>{{pagelink:R4BundleExampleHbA1cReport}}<br>{{pagelink:R4BundleExampleHBsAgReport}}<br>{{pagelink:R4BundleExampleHPVReport}}<br>{{pagelink:R4BundleExampleFullBloodCountReport}}<br>{{pagelink:R4BundleExampleLipidsandHbA1cReport}}<br>{{pagelink:R4BundleExampleLFTandUandEReport}}<br>{{pagelink:R4BundleExampleGTTReport}}<br>{{pagelink:R4BundleExampleUrineMCSReport}}<br><br>
    <b>UK Core Examples</b> - Examples from the UK Core Implementation Guide.<br>
    <a href="https://simplifier.net/guide/uk-core-implementation-guide-stu2/home/examples/examplesindex/Example-UKCore-Specimen-BloodSpecimen?current">UKCore-Specimen-BloodSpecimen-Example</a><br>
    <a href="https://simplifier.net/guide/uk-core-implementation-guide-stu2/home/examples/examplesindex/Example-UKCore-Specimen-Extension-SpecialHandling?current">UKCore-Extension-SpecialHandling-Example</a><br>
    <a href="https://simplifier.net/guide/uk-core-implementation-guide-stu2/home/examples/examplesindex/Example-UKCore-Specimen-Extension-BodySiteReference?current">UKCore-Extension-BodySiteReference-Example</a><br><a href="https://simplifier.net/guide/uk-core-implementation-guide-stu2/home/examples/examplesindex/Example-UKCore-Specimen-UrineSpecimen?current">UKCore-Specimen-UrineSpecimen-Example</a><br>
</div>

### Additional Guidance
The following additional guidance **SHOULD** be applied when implementing this profile. It **SHOULD** be used in conjunction with the profile definition presented above and the Profile Specific Implementation Guidance for `UKCore-Specimen` in the [UK Core Implementation Guide](https://simplifier.net/guide/uk-core-implementation-guide-stu2/home/profilesandextensions/profile-ukcore-specimen?current).

---

### `identifier`
FHIR provides two data elements for conveying specimen related identifiers:
* `Specimen.identifier`: this is defined in the base FHIR specification as "Id for specimen" and has a cardinality of 0..*.
* `Specimen.accessionIdentifier`: this is defined in the base FHIR specification as "The identifier assigned by the lab when accessioning specimen(s)." and has a cardinality of 0..1.

If multiple laboratories are involved with processing a test (as is the case for send-away or referred tests), it is not possible to assign more than one `Specimen.accessionIdentifier` because the data element has a maximum cardinality of 1.

It is therefore recommended that:
* `Specimen.identifier` is used to convey all specimen related identifiers, including those assigned by the requesting organisation and the laboratory (or multiple laboratories where applicable). Each organisation **SHOULD** append their local identifier to the identifier array as needed, ensuring either the system or assigner is able to disambiguate any identifiers from possibly overlapping numbers from other organisations.
* `Specimen.accessionIdentifier` **SHOULD NOT** be used.

---

### `accessionIdentifier`
This data element **SHOULD NOT** be used, as described in the guidance for `Specimen.identifier` above.  

---

### `status`
This **SHALL** be populated as follows: 
* `available`: when the specimen is present and in a usable condition
* `unavailable`: when the specimen is not available, for example it has been lost
* `unsatisfactory`: when the specimen cannot be used, for example because of a broken container or contamination

---

### `request`
Reference to the `ServiceRequest` that the specimen relates to. This should only be used when a test was requested before the specimen was collected.

**Note:** It is also possible to link a `ServiceRequest` to a `Specimen` using the `ServiceRequest.specimen` data element. This should be used when a test is requested and the specimen has already been collected.

For further information refer to:

* the description of the {{pagelink:R4ServiceRequest}} profile in this implementation guide, and
* the notes relating to the use of the [ServiceRequest](https://hl7.org/fhir/R4/servicerequest.html#notes) resource in the base FHIR specification.
