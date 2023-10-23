# {{page-title}}

## The HL7 FHIR® standard
The HL7 FHIR® standard creates a common foundation on which a variety of different solutions are implemented. The resources contained in the specification usually require further adaptation to particular health or social care use cases; this adaptation is referred to as "profiling" and the resulting artefacts as "profiles". 

## General profiling approach
The checklist below was adhered to when developing a draft NHS England profile suitable for progression to Clinical and Technical Assurance.

- Ensure a NHS England IG profile exists and consider the status of the profile before deriving a NHS England profile.


## Approach to StructureDefinition elements
- **Identifiers** - Where existing NHS Digital IG profiles have applied slicing and profiling to identifiers, this will be recreated in the NHS England IG profiles, then evaluated during Clinical and Technical assurance.
- **Removal of elements** - No elements will be removed from the FHIR assets for the NHS England IG profiles during initial profiling prior to Clinical and Technical Assurance. 
- **Experimental element** - The FHIR specification defines the 'StructureDefinition.experimental' element as the following, when set to ‘true’:
'This structure was authored for testing purposes (or education/evaluation/marketing), and is not intended for genuine usage.'
(Source: <a href="http://hl7.org/fhir/r4/index.html">HL7</a>). Currently there is no requirement in the NHSE IG  to set the experimental element as ‘true’ or ‘false’, so this field should remain in the default view (undefined).

---