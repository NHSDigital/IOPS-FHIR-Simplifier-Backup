## Technical Patterns

The PatientFlag API and all it's sub-domains use the [FHIR REST](http://hl7.org/fhir/r4/http.html) paradigm.

**Note:** this specification uses "PatientFlag" as a proxy for the FHIR Flag resource. "PatientFlag" is therefore the API endpoint to retrieve details of Flags relating to patients. PatientFlag uses the search parameters associated with the FHIR Flag resource. Although the endpoint is called PatientFlag, it does return Flag resources on search, and accept Flag resources to create patient flags.

### FHIR REST

Implementations SHOULD provide capability to offer and consume RESTful interactions to allow an efficient implementation of the required API.

Implementations SHALL provide capability to offer and consume basic CRUD (create, read/search, update, delete) interactions via http.

Implementations SHALL provide capability to offer and consume additional FHIR REST functionality, e.g. Transaction support, Conditional Update etc. as required in the relevant, specific implementation guidance in play for a given integration.

Implementers SHALL be aware of and compliant with standard FHIR REST functionality defined in the HL7 FHIR Specification on topics:

* [FHIR Search](http://www.hl7.org/fhir/R4/search.html)
* [SearchParameters](https://www.hl7.org/fhir/R4/searchparameter.html)

and in using:

* [Bundle](https://hl7.org/fhir/r4/bundle.html)  
* [Transaction](https://hl7.org/fhir/r4/http.html#transaction)  



### BaseURL and Environments

Queries in this specification use ```[baseURL]``` as stand in for the first part of the server path. In practice, this varies by environment:

| Purpose | Base URL |
|-|-|
| Sandbox | https://sandbox.api.service.nhs.uk/patient-flags-api/FHIR/R4 |
| Integration test | https://int.api.service.nhs.uk/patient-flags-api/FHIR/R4 |
| Production | https://api.service.nhs.uk/patient-flags-api/FHIR/R4 |


### Capability Statements

Applications/systems offering an API SHALL document resources and interactions supported via a CapabilityStatement resource available as per [CapabilityStatement](http://hl7.org/fhir/r4/capabilitystatement.html) and [Conformance Rules](http://hl7.org/fhir/r4/conformance-rules.html) pages of the FHIR (Release 4) Specification.

Applications/systems integrating with an API SHALL document resources and interactions supported via a CapabilityStatement resource available as per [CapabilityStatement](http://hl7.org/fhir/r4/capabilitystatement.html) and [Conformance Rules](http://hl7.org/fhir/r4/conformance-rules.html) pages of the FHIR (Release 4) Specification.

### Specific Implementations

Implementations SHALL provide all functionality additionally required by their specification and/or Implementation guidance.
This may constitute:

* Standard integration requirements regarding authorisation, logging etc.
* Additional FHIR constraints
* Additional non-FHIR business rules and process requirements

---
