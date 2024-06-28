## {{page-title}}

The GP Connect Send Document capability uses elements contained within the {{pagelink:Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-Composition-1}} resource to identify a document, using SNOMED-CT.


### `Composition.type`

A mandatory <span class="mro-circle mandatory"></span> element used to represent the type of composition being sent using a SNOMED-CT code from the PRSB Document Naming standard (also know as the Clinical Document Indexing standard).

For example:

- [734163000 | Care plan (record artifact) |](https://termbrowser.nhs.uk/?perspective=full&conceptId1=734163000)

<br />

### `Composition.extension.careSettingTypeExtension`

A required  <span class="mro-circle required"></span> element used to represent the service that is sending the document using a SNOMED-CT code from the FHIR UK Core [Care Setting Type valueset](https://simplifier.net/hl7fhirukcorer4/ukcore-caresettingtype).

For example:

- [789718008 | Cardiology service (qualifier value) |](https://termbrowser.nhs.uk/?perspective=full&conceptId1=7897180080)

<br />

### `Composition.event`

An optional <span class="mro-circle optional"></span> element used to represent additional context about the document using a value from SNOMED-CT. The `period` element may also be populated.

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <b>Note</b>: A use-case has not been identifier for populating the <code>detail</code> element.
</div>

---