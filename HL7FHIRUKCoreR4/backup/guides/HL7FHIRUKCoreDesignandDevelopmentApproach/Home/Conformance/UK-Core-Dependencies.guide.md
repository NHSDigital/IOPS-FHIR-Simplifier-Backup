# {{page-title}}

The UK Core by nature does have some dependencies. Most of the dependencies are things which the UK Core must be conformant with, however some are less tightly bound and this section details the dependencies and how they are managed. This section details the following dependency information:

- What is the dependency? 
- How is it managed?
- Any impact on UK Core development

## The FHIR Standard

The UK Core SHALL align with (be conformant with) the <a href="https://simplifier.net/guide/HL7FHIRUKCoreDesignandDevelopmentApproach/Home/Glossary#G1" Target="_blank">FHIR standard</a> which is still evolving. It has some normative parts, but is currently a Standard for Trial Use. For this reason, there will potentially be several versions of the UK Core Implementation guide for each release of the FHIR Standard. Each UK Core based on a FHIR version will have a separate and independent life cycle. There is currently only a R4 version and no plans to migrate to R5. The choice of when to introduce a new version of the UK Core for a given FHIR version will be only be made after full consultation and agreement with the UK FHIR Community.  
The approach of building a UK Core based on a fixed version of the FHIR standard means that the dependency is only to be conformant with the chosen FHIR version. This is currently FHIR R4. 

The UK Core is built and managed using the Simplifier platform which is a FHIR server and supports the ability to select a version of FHIR as a dependency. This dependency is then managed by the platform. The platform has built in quality and conformance rules which validate all the UK Core FHIR assets that are added to an Implementation Guide against the FHIR Standard.
 
## NHS Data Model and Dictionary

The UK Core uses the NHS Data Model and Dictionary as an allowable CodeSystem in many UK Core ValueSets. The scope of the NHS Data Dictionary is England, whereas the UK Core is UK wide. The UK Core ensures that the NHS Data Dictionary can be used where appropriate for English use cases. The principle for all UK Core ValueSets binding strength can be found within the {{pagelink:FHIRAssetDesign}}, which facilitates the use of Data Dictionary for English use cases. As a result of the Clinical and Technical Assurance process, the use of the NHS Data Dictionary can be mandated, if required, in the English implementation guides that are derived from the UK Core. 

## NHS Wales Data Dictionary 
The <a href="https://simplifier.net/guide/HL7FHIRUKCoreDesignandDevelopmentApproach/Home/Glossary#G15" Target="_blank">NHS Wales Data Dictionary</a> is a guide to the definitions, collection and interpretation of nationally agreed data standards adopted by the NHS in Wales. It has been prepared for the use of everyone who is actively involved in the collection of data and the use of information in NHS Wales. The principle for all UK Core ValueSets binding strength can be found within the {{pagelink:FHIRAssetDesign}}, which facilitates the use of the Welsh Data Dictionary for Welsh use cases. As a result of the Clinical and Technical Assurance process, the use of the NHS Wales Data Dictionary can be mandated, if required, in any Welsh implementation guides that are derived from the UK Core.   

## SNOMED CT 
<a href="https://simplifier.net/guide/HL7FHIRUKCoreDesignandDevelopmentApproach/Home/Glossary#G16" Target="_blank">SNOMED CT</a> is used as a CodeSystem for most if not all "clinical" coded values. SNOMED CT is dynamic by nature and this is acceptable at the UK Core level. The UK Core never fixes profile bindings to a given SNOMED CT concept but uses <a href="https://simplifier.net/guide/HL7FHIRUKCoreDesignandDevelopmentApproach/Home/Glossary#G16" Target="_blank">Expression Constraint Language (ECL)</a> statements to support this dynamic terminology. There is therefore no real dependency, however derived implementations may by design introduce a dependency on SNOMED CT but where that is the case the derived implementation SHALL manage that dependency.

## Dictionary of medicines and devices (dm+d)
<a href="https://simplifier.net/guide/HL7FHIRUKCoreDesignandDevelopmentApproach/Home/Glossary#G17" Target="_blank">dm+d</a> is used as a CodeSystem for a small number of coded values, mainly around medications and allergies. dm+d is dynamic by nature and this is acceptable at the UK Core level. The UK Core never fixes profile bindings to a given dm+d concept but will use a statement which defines the allowed content to support this dynamic terminology.There is therefore no real dependency, however derived implementations may by design introduce a dependency on dm+d but where that is the case the derived implementation SHALL manage that dependency.

## LOINC
LOINC Codesystems are rarely used within the UK, with the majority of clinical codes being SNOMED CT. HL7 does mandate LOINC in some profiles, for instance <a href="https://www.hl7.org/fhir/observation-vitalsigns.html>Observation-vitalsigns</a> profile and its derivatives, where certain binding strengths are `extensible` or `required`. To conform to FHIR these have been kept within the UK Core profiles derived from HL7 but an equivalent SNOMED CT code has been added to the `coding` element for use and validation purposes.

## Alignment with the other standards
The UK Core has no dependency on ohter standards, however alignment with the following is desirable and feedback from vendors has confirmed that this is their requirement too:
- <a href="https://wiki.ihe.net/index.php/Category:FHIR">IHE</a>, 
- <a href="https://openehr.org/">openEHR</a>, 
- <a href="https://theprsb.org/">PRSB</a>
- <a href="https://hl7.eu/fhir/index.html">HL7 Europe</a>, 
- <a href="https://www.hl7.org/fhir/us/core/">US Core</a>, 
- <a href="https://build.fhir.org/ig/hl7au/au-fhir-core/">AU Core</a>.

---

