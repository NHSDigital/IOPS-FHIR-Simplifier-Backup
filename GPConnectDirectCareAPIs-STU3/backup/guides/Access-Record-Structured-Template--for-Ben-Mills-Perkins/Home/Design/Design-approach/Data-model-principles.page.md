## {{page-title}}

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
<b>Summary</b>: High-level design principles related to the FHIR® profiles
</div>

### Introduction
GP Connect versions 1.x use the [FHIR STU3](http://hl7.org/fhir/STU3/) standard to specify the API and data models (known as profiles).


### Profiling principles

When creating the profiled FHIR resources GP Connect have aimed to improve interoperability by:

- aligning, where available, to the CareConnect profiles produced by INTEOPen
- storing profiles on [GitHub](https://github.com/nhsconnect/gpconnect-fhir)

- publishing profiles to [fhir.nhs.uk](https://fhir.nhs.uk/)

- carrying the major version in the name of a profile (for example, gpconnect-patient-1) and major/minor version within StructureDefinition/Conformance.

- not mandating profile elements unless this cardinality will apply for all existing and future use cases

- applying must support flags to elements which hold key information within the resources


### GP Connect FHIR profiles
Please see the {{pagelink:Home/Build/FHIR-development/FHIR--resources.page.md}} guidance page for further information.

---

</br>