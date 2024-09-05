## {{page-title}}

### Encounter

UK Core Profile {{link:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Encounter}}

   
    GET [base]/Encounter?param1=value&...{&_format=[mime-type]}
 

Search Parameters [Encounter](https://hl7.org/fhir/R4/Encounter.html#search)

The following search parameter combinations should be supported:

| Parameters | Type |Modifiers | Optionality | IHE QEDm |HL7 UK CORE ACCESS |
|--
| patient |	reference	| |  SHALL |&check; | |
| patient + date | reference + date |date modifiers ‘ge’,‘le’,’gt’,’lt’ | SHALL |&check; | |