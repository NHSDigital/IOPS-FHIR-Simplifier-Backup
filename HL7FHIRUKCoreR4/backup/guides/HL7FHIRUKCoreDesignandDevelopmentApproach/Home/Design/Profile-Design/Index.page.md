# {{page-title}}

## The HL7 FHIR® standard
The HL7 FHIR® standard creates a common foundation on which a variety of different solutions are implemented. The resources contained in the specification usually require further adaptation to particular health or social care use cases; this adaptation is referred to as "profiling" and the resulting artefacts as "profiles". 

## General profiling approach
The checklist below was adhered to when developing a draft UK Core profile suitable for progression to Clinical and Technical Assurance.
- Use any corresponding CareConnect profile as a starting point
For each profile, where a CareConnect STU3 profile exists, refer to it as a starting point for the UK Core FHIR R4 profiling exercise,
- Consider the resource changes between FHIR STU3 and R4 versions
Analyse the changes in the FHIR standard between FHIR STU3 version and FHIR R4,for example the addition or deletion of any elements and the introduction of new or updated terminology assets in the R4 version.
- Referencing to resources SHOULD be to the base resource rather than a UK Core Profile, unless agreed.

## Approach to StructureDefinition elements
- **Identifiers** - Where existing CareConnect STU3 profiles have applied slicing and profiling to identifiers, this will be recreated in the UK Core profiles, then evaluated during Clinical and Technical assurance.
- **Removal of elements** - No elements will be removed from the FHIR assets for the UK Core profiles during initial profiling prior to Clinical and Technical Assurance. 
- **Experimental element** - The FHIR specification defines the 'StructureDefinition.experimental' element as the following, when set to ‘true’:
'This structure was authored for testing purposes (or education/evaluation/marketing), and is not intended for genuine usage.'
(Source: <a href="http://hl7.org/fhir/r4/structuredefinition.html#metadata">HL7</a>). Currently there is no requirement in the UK Core to set the experimental element as ‘true’ or ‘false’, so this field should remain in the default view (undefined).

---

