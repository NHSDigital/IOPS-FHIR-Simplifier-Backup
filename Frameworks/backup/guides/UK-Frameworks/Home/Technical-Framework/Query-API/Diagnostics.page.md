## {{page-title}}

### DiagnosticReport
   
    GET [base]/DiagnosticReport?param1=value&...{&_format=[mime-type]}
 

UK Core Profile {{link:https://fhir.hl7.org.uk/StructureDefinition/UKCore-DiagnosticReport}}

Search Parameters [DiagnositcReport](https://hl7.org/fhir/R4/diagnosticreport.html#search)

The following search parameter combinations should be supported:

| Parameter| Type | Modifiers | Optionality |  IHE QEDm | HL7 UK CORE ACCESS |
|--
| patient + category | reference + token | | SHALL | &check; |
| patient + category + code | reference + token	| | SHALL| 	&check; |	
| patient + category + date| 	reference + token + date| 	date modifiers ‘ge’,‘le’,’gt’,’lt’ |	SHOULD | &check; | |	
| patient + category + code + date | reference + token + date | date modifiers ‘ge’,‘le’,’gt’,’lt’ | SHOULD |&check; | | 

### Observation
   
    GET [base]/Observation?param1=value&...{&_format=[mime-type]}
 

UK Core Profile {{link:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation}}

Search Parameters [Observation](https://hl7.org/fhir/R4/observation.html#search)

The following search parameter combinations should be supported:

| Parameter| Type | Modifiers | Optionality |  IHE QEDm | HL7 UK CORE ACCESS |
|--
| patient + category| reference + token	|| SHALL| &check; | |	
| patient + category + code | reference + token || 	SHALL|&check; ||	
| patient + category + date | reference + token + date | date modifiers ‘ge’,‘le’,’gt’,’lt’ | SHOULD | &check;||	
| patient + category + code + date | reference + token + date | date modifiers ‘ge’,‘le’,’gt’,’lt’ | SHOULD |&check; ||	
| patient + date | reference + date | date modifiers ‘ge’,‘le’,’gt’,’lt’ | ||	
| patient + code + date | reference + token + date | date modifiers ‘ge’,‘le’,’gt’,’lt’ | | |	
