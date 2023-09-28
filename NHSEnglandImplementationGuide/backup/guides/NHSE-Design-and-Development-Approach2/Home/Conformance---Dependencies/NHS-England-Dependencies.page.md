# {{page-title}}

The NHS England by nature does have some dependencies. Most of the dependencies are things which the NHS England must be conformant with, however some are less tightly bound and this section details the dependencies and how they are managed. This section details the following dependency information:

- What is the dependency? 
- How is it managed?
- Any impact on UK Core development

## The FHIR Standard

The NHS England Implementation guide and FHIR assets SHALL align with (be conformant with)the [FHIR standard](https://simplifier.net/guide/HL7FHIRUKCoreDesignandDevelopmentApproach/Home/Glossary#G1 "Title") which is still evolving. It has some normative parts but is currently a Standard for Trial Use. For this reason, there will potentially be several versions of the NHS England Implementation guide for each release of the FHIR Standard. Each NHS England Implementation guide based on a FHIR version and UK Core version will have a seperate and independent life cycle. There is currently only a R4 version and no plans to migrate to R5. The choice of when to introduce a new version of the NHS England Implementation for a given FHIR version will only be made after the UK Core has migrated to the new version.

The approach of building a NHS England Implementation Guide based on a fixed version of the FHIR standard means that the dependency is only to be conformant with the chosen FHIR version. This is currently FHIR R4.

The NHS England Implementation Guide is built and managed using the Simplifier platform which is a FHIR server and supports the ability to select a version of FHIR as a dependency. This dependency is then managed by the platform. The platform has built in quality and conformance rules which validate all the NHS England FHIR assets that are added to an Implementation Guide against the FHIR Standard and the FHIR UK Core.

## FHIR UK Core

The NHS England IG has a dependency on the FHIR UK Core. There may be multiple versions of UK Core that NHS England IGs can be dependant on. These are managed by the simplifier platform and the NHS England Packages allow validation. 

## NHS Data Model and Dictionary

The UK Core uses the NHS Data Model and Dictionary as an allowable CodeSystem in many UK Core ValueSets. The scope of the NHS Data Dictionary is England, whereas the UK Core is UK wide. The UK Core ensures that the NHS Data Dictionary can be used where appropriate for English use cases. The principle for all UK Core ValueSets binding strength can be found within the [Asset Design](https://simplifier.net/guide/NHSE-Design-and-Development-Approach2/Home/Asset-Design?version=current), which facilitates the use of Data Dictionary for English use cases. As a result of the Clinical and Technical Assurance process, the use of the NHS Data Dictionary can be mandated, if required, in the English implementation guides that are derived from the UK Core. 

## SNOMED CT 
<a href="https://simplifier.net/guide/HL7FHIRUKCoreDesignandDevelopmentApproach/Home/Glossary#G16" Target="_blank">SNOMED CT</a> is used as a CodeSystem for most if not all "clinical" coded values. SNOMED CT is dynamic by nature and this is acceptable at the NHS England level. The NHS England IG never fixes profile bindings to a given SNOMED CT concept but uses <a href="https://simplifier.net/guide/HL7FHIRUKCoreDesignandDevelopmentApproach/Home/Glossary#G16" Target="_blank">Expression Constraint Language (ECL)</a> statements to support this dynamic terminology. There is therefore no real dependency, however the NHS England implementations may by design introduce a dependency on SNOMED CT but where that is the case the derived implementation SHALL manage that dependency.

## Dictionary of medicines and devices (dm+d)
<a href="https://simplifier.net/guide/HL7FHIRUKCoreDesignandDevelopmentApproach/Home/Glossary#G17" Target="_blank">dm+d</a> is used as a CodeSystem for a small number of coded values, mainly around medications and allergies. dm+d is dynamic by nature and this is acceptable at the NHS England level. The NHS England IG never fixes profile bindings to a given dm+d concept but will use a statement which defines the allowed content to support this dynamic terminology.There is therefore no real dependency, however derived implementations such as the NHS England IG may by design introduce a dependency on dm+d but where that is the case the derived implementation SHALL manage that dependency.

## Alignment with the US Core
The NHS England IG has no dependency on the <a href="https://simplifier.net/guide/HL7FHIRUKCoreDesignandDevelopmentApproach/Home/Glossary#G17" Target="_blank">US Core</a>, but will inherit this and any other dependency that is applicable from the UK Core that is not specially detailed here. 

---

