## {{page-title}}

When creating the profiled FHIR resources GP Connect have aimed to improve interoperability by:

- aligning, where available, to the CareConnect profiles produced by INTEROPen
- storing profiles on [GitHub](https://github.com/nhsconnect/gpconnect-fhir)
- publishing profiles to [fhir.nhs.uk](https://fhir.nhs.uk/)
- carrying the major version in the name of a profile (for example, gpconnect-patient-1) and major/minor version within StructureDefinition/Conformance.
- not mandating profile elements unless this cardinality will apply for all existing and future use cases
- applying must support flags to elements which hold key information within the resources