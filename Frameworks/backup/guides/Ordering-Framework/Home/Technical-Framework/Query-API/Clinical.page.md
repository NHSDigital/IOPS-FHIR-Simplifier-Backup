## {{page-title}}

### AllergyIntolerance

   
    GET [base]/AllergyIntolerance?param1=value&...{&_format=[mime-type]}
 

UK Core Profile {{link:https://fhir.hl7.org.uk/StructureDefinition/UKCore-AllergyIntolerance}}

Search Parameters [AllergyIntolerance](https://hl7.org/fhir/R4/AllergyIntolerance.html#search)

The following search parameter combinations should be supported:

| Parameters | Type |Modifiers | Optionality | IHE QEDm |HL7 UK CORE ACCESS |
|--
| patient| reference|| SHALL | &check; | &check; |
| patient + date| reference + date|| SHOULD|  | &check; |
| patient + clinical_status	| reference + token| |	SHOULD	|  | &check; |
| patient + last_date | reference + date| |	SHOULD	|  | &check; |	
| _id| token | | SHOULD | | &check; |

### Condition
   
    GET [base]/Condition?param1=value&...{&_format=[mime-type]}
 

UK Core Profile {{link:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Condition}}

Search Parameters [Condition](https://hl7.org/fhir/R4/Condition.html#search)

The following search parameter combinations should be supported:

| Parameters | Type | Modifiers |Optionality | IHE QEDm |HL7 UK CORE ACCESS |
|--
| patient| reference| | SHALL| &check; |  |
| patient + category| reference + token| | SHOULD| &check; |  |
| patient + clinical-status| reference + token| | SHOULD| &check; |  |
| patient + recorded-date| reference + date| |	SHOULD	| &check; |  |

### Procedure
   
    GET [base]/Procedure?param1=value&...{&_format=[mime-type]}
 

UK Core Profile {{link:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Procedure}}

Search Parameters [Procedure](https://hl7.org/fhir/R4/Procedure.html#search)

The following search parameter combinations should be supported:

| Parameters | Type |Modifiers | Optionality | IHE QEDm |HL7 UK CORE ACCESS |
|--
| patient| reference| |	SHALL| &check; |  |
| patient + date| 	reference + date| 	date modifiers ‘ge’,‘le’,’gt’,’lt’| 	SHALL	| &check; |  |
