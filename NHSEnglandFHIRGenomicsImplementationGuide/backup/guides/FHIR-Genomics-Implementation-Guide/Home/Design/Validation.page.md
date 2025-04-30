## {{page-title}}

Validation of FHIR structures is expected to be performed against the UK Core package listed within the IG dependencies.
This validation can be performed using any [open source FHIR validator](https://www.hl7.org/fhir/validation.html) (the current Alpha FHIR validation is being performed via the [HAPI FHIR validation tool](https://hapifhir.io/hapi-fhir/docs/validation/instance_validator.html)).

Validation of codes is split into 2 parts:
* Validation of codes defined within FHIR CodeSystems, either FHIR R4, UK Core or Genomics specific will occur locally on the central broker, via loading in of the associated packages.
* Validation of codes defined within external terminologies is expected to occur against central terminology servers, such as the [NHS England OntoServer](https://digital.nhs.uk/services/terminology-server). For the alpha, this is currently limited to validation of HPO and SNOMED CT terms against the versions loaded into the terminology server. Discussions are ongoing for support of further genomics specific terminologies and nomenclatures used within [Genomic Reporting](https://build.fhir.org/ig/HL7/genomics-reporting/codings.html)
    - The NHS Ontology Server will fail to validate the Fully Specified Name (FSN), so if a display term is provided, a synonym SHALL be used. Relaxation of this requirement will be investigated within the Order Management Beta. 

Users will be able to validate resources against the Genomics IG (UK Core STU3 plus genomic specific business logic) by using the Alpha implementation of the $validate operation.