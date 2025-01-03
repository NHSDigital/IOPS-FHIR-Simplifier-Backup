## {{page-title}}

### 0.4.3

Date released: 03/01/2025

[GitHub Release/Changelog](https://github.com/NHSDigital/NHSDigital-FHIR-Genomics-ImplementationGuide/releases/tag/v0.4.3)

- Updates to Specimen ConceptMaps
- Updated dependency to latest UK Core package to pick up changes to Sample State CodeSystem
- Removed incorrect Observations for Risk of Infection (captured under Specimen) and Disease Status (replaced with Condition)
- Correction to targeting of UK Core profiles
- Addition of Patient examples for no NHS number and where demographics are recorded on PDS

### 0.4.2

Date released: 01/10/2024

[GitHub Release/Changelog](https://github.com/NHSDigital/NHSDigital-FHIR-Genomics-ImplementationGuide/releases/tag/v0.4.2)

- Update to UK Core dependency with fixes to FundingCategory and SampleCategory CodeSystems and ConditionBodyStructure Extension

### 0.4.1

Date released: 30/09/2024

[GitHub Release/Changelog](https://github.com/NHSDigital/NHSDigital-FHIR-Genomics-ImplementationGuide/releases/tag/v0.4.1)

- Updates to IG based on feedback during Alpha broker development (closed issues addressed by this release can be found on the [project issue list](https://simplifier.net/NHS-Digital-FHIR-Genomics-Implementation-Guide/~issues?status=Closed), opened between 01/03/2024 and 30/09/2024)
- Major changes to modelling
- Fixed referencing issues between resources and incorrect modelling of concepts, e.g. consanguinity, absence of an observation, HPO etc.
- Updated guidance to reflect modelling issues above
- Addition of SearchParamaters and GraphDefinitions, and associated IG pages
- Addition of ConceptMaps, CodeSystems, ValueSets and NamingSystems to align with MDSv1.04
- Addition of guidance to support UGR use cases, including addition of DocumentReference and Operations
- Further guidance and assets to illustrate CRUD capabilities and responses
- Updated dependency to UK Core STU3 and updated concept codes to align with latest release of SNOMED CT
- Developed guidance for Task/Specimen status, businessStatus, input and output population

### 0.3.2

Date released: 12/04/2024

[GitHub Release/Changelog](https://github.com/NHSDigital/NHSDigital-FHIR-Genomics-ImplementationGuide/releases/tag/v0.3.2)

- Update to dependencies, removal of dependency on NHSDigital package
- Addition of Task.input/output elements referencing Specimen resources in examples

### 0.3.1

Date released: 14/03/2024

[GitHub Release/Changelog](https://github.com/NHSDigital/NHSDigital-FHIR-Genomics-ImplementationGuide/releases/tag/v0.3.1)

- Minor update to dependencies (breaking change to modelling of Extension-UKCore-BirthSex on UKCore-Patient)

### 0.3.0

Date released: 01/03/2024

[GitHub Release/Changelog](https://github.com/NHSDigital/NHSDigital-FHIR-Genomics-ImplementationGuide/releases/tag/v0.3.0)

- Updates to IG based on responses to review for v0.2.0 (closed issues addressed by this release can be found on the [project issue list](https://simplifier.net/NHS-Digital-FHIR-Genomics-Implementation-Guide/~issues?status=Closed), opened between 06/10/2023 and 01/03/2024)
- Additional guidance on design pages on interactions with the Genomic Order Management Broker
- Additional guidance on profile pages providing guidance on population of elements
- Additional Clinical Scenarios outside of 'happy path' WGS and non-WGS workflows and addition of associated FHIR examples
- Alignment of Task CodeSystems with NGTP
- Update of IG template to new NHS England branding

### 0.2.0

Date released: 06/10/2023

[GitHub Release/Changelog](https://github.com/NHSDigital/NHSDigital-FHIR-Genomics-ImplementationGuide/releases/tag/v0.2.0)

- Dependencies updated to UK Core STU2 Ballot pre-release package 
- Removal of resources which have been promoted to UK Core
- Addition of HL7v2 mapping for minimum data set
- Addition of WGS and non-WGS Rare and Inherited Disease Scenarios

### 0.1.0

Date released: 27/03/2023

[GitHub Release/Changelog](https://github.com/NHSDigital/NHSDigital-FHIR-Genomics-ImplementationGuide/releases/tag/v0.1.0)

- Initial draft of the Genomics Implementation Guide
- Logical model currently profiled into specific Genomics resources, these will be merged into NHS Digital in a future release
- This version has not gone through Clinical and Technical assurance

