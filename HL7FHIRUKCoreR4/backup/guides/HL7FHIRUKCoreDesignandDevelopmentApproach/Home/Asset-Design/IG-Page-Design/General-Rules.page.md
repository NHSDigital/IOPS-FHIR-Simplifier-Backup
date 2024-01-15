## General Rules 

- Information SHALL be unique to UK Core. There SHOULD NOT be any duplication of HL7 FHIR content nor any information within the profile unless it gives context for additional UK Core information. 
- Information SHALL NOT contradict HL7 FHIR. 
- Conformance language SHALL be written in accordance with <a href="https://build.fhir.org/conformance-rules.html#conflang">https://build.fhir.org/conformance-rules.html#conflang</a> . 
- External links to HL7 FHIR SHALL be the same version as UK Core. 
- Each header SHALL be in Title case unless the header wording is an element, then is SHALL be in camelCase and as an inline code. 
- Elements and values SHALL be written as an inline code. 
- The first index title will be in the markdown form as \# Header1. 
- Each following page first title shall be in the from \## Header2. 
- Sub headers within these pages SHALL be in the form \### Header3 or \#### Header4 where needed
- Each table SHALL be in HTML code.
- All lists SHOULD be in alphabetical order. 
- Line breaks SHALL be written as \<br>. 
- The end of each page SHALL have a page break, denoted by three dashes. 
- Codenames that are not headers SHALL be written in absolute terms and as inline code, e.g. \`Patient.contact.name\` 
- FHIR assets names SHALL match the casing of their defintion on HL7 FHIR. Typically this will be written in PascalCase, such as ValueSet or CodeSystem.
- When refering to SNOMED CT, it SHALL be written in capitals.
- When refering to SNOMED CT codes, the words Concept, Description, and Id SHALL be used in Title case.
- FHIR elements SHALL be fully qualified when discussed in guidance, e.g. `Procedure.note.authorReference` rather than `note.author`
- CSS shall be used to control table column widths
- All asset and major IG page design changes will be logged in the Version History change log

---