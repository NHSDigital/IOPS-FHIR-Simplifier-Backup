## Technical patterns

The Patient Flag API and all it's sub-domains use the [FHIR REST](http://hl7.org/fhir/r4/http.html) paradigm.

### FHIR REST

Implementations SHOULD provide capability to offer and consume RESTful interactions to allow an efficient implementation of the required API.

Implementations SHALL provide capability to offer and consume basic CRUD (create, read/search, update, delete) interactions via http.

Implementations SHALL provide capability to offer and consume additional FHIR REST functionality, e.g. Transaction support, Conditional Update etc. as required in the relevant, specific Implementation guidance in play for a given integration.

Implementers SHALL be aware of and compliant with standard FHIR REST functionality defined in the HL7 FHIR Specification on topics:

* [FHIR Search](http://www.hl7.org/fhir/R4/search.html)
* [SearchParameters](https://www.hl7.org/fhir/R4/searchparameter.html)

and in using:

* [Bundle](https://hl7.org/fhir/r4/bundle.html)  
* [Transaction](https://hl7.org/fhir/r4/http.html#transaction)  
* [Upsert](https://hl7.org/fhir/r4/http.html#upsert)  



### Capability statements

Applications/systems offering an API SHALL document resources and interactions supported via a CapabilityStatement resource available as per [CapabilityStatement](http://hl7.org/fhir/r4/capabilitystatement.html) and [Conformance Rules](http://hl7.org/fhir/r4/conformance-rules.html) pages of the FHIR (Release 4) Specification.

Applications/systems integrating with an API SHALL document resources and interactions supported via a CapabilityStatement resource available as per [CapabilityStatement](http://hl7.org/fhir/r4/capabilitystatement.html) and [Conformance Rules](http://hl7.org/fhir/r4/conformance-rules.html) pages of the FHIR (Release 4) Specification.

### Specific implementations

Implementations SHALL provide all functionality additionally required by their specification and/or Implementation guidance.
This may constitute:

* Standard integration requirements regarding e.g. Authorization, Logging etc.
* Additional FHIR constraints
* Additional non-FHIR business rules and process requirements


### Reasonable Adjustments

Reasonable Adjustments data model includes additional detail resources that record:

  * individual reasonable adjustments - modelled as instances of [EnglandFlagPatientFlagAdjustment](https://simplifier.net/nhs-england-programme-implementation-guides/england-flag-patientflag-adjustment/~overview) profile
  * optionally, conditions for which reasonable adjustments are being made - modelled as instances of [EnglandConditionPatientFlag](https://simplifier.net/nhs-england-programme-implementation-guides/england-condition-patientflag/~overview) profile

---
