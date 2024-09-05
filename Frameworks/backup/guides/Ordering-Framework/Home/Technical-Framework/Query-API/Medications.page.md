## {{page-title}}

### Immunization
   
    GET [base]/Immunization?param1=value&...{&_format=[mime-type]}
 

UK Core Profile {{link:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Immunization}}

Search Parameters [Immunization](https://hl7.org/fhir/R4/Immunization.html#search)

The following search parameter combinations should be supported:

| Parameters | Type | _include | Modifiers | Optionality | IHE QEDm |HL7 UK CORE ACCESS |
|--
| patient | reference | | | SHALL |&check; | &check;|	 
| _id | token | | | SHOULD | | &check;|	
| patient + date | reference + date | | |SHOULD | | &check;|	
| patient + status | reference + token | | | SHOULD	 | | &check;|

### MedicationStatement
   
    GET [base]/MedicationStatement?param1=value&...{&_format=[mime-type]}
 
UK Core Profile {{link:https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationStatement}}

Search Parameters [MedicationStatement](https://hl7.org/fhir/R4/MedicationStatement.html#search)

The following search parameter combinations should be supported:

| Parameters | Type | _include | Modifiers | Optionality | IHE QEDm |HL7 UK CORE ACCESS |
|--
| patient| reference| MedicationStatement :medication | | SHALL |&check; |	&check; (_include not supported)	| 
| _id |token | || SHOULD	| | &check; | 
| patient + effective | reference + date | || SHOULD	| | &check; | 
| patient + status | reference + token | | | SHOULD	| | &check; | 

### MedicationRequest
   
    GET [base]/MedicationRequest?param1=value&...{&_format=[mime-type]}
 
UK Core Profile {{link:https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationRequest}}

Search Parameters [MedicationRequest](https://hl7.org/fhir/R4/MedicationRequest.html#search)

The following search parameter combinations should be supported:

| Parameters | Type | _include | Modifiers | Optionality | IHE QEDm |HL7 UK CORE ACCESS |
|--
| patient | reference | MedicationRequest<br/>:medication | | SHALL | &check; 	| &check; (_include not supported) |
| _id | token | | |SHOULD |  | &check; |	
| patient + authoredon | reference + date | | |SHOULD	|  | &check; |
| patient + status | reference + token | | |SHOULD |  | &check; |


### MedicationAdministration
   
    GET [base]/MedicationAdministration?param1=value&...{&_format=[mime-type]}
 
UK Core Profile {{link:https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationAdministration}}

Search Parameters [MedicationAdministration](https://hl7.org/fhir/R4/MedicationAdministration.html#search)
The following search parameter combinations should be supported:

| Parameters | Type | _include | Modifiers| Optionality | IHE QEDm |HL7 UK CORE ACCESS |
|--
| patient | reference | | | SHALL | | &check;|	 
| _id | token | | | SHOULD | | &check;|	
| patient + effective_time | reference + date | | |SHOULD | | &check;|	
| patient + status | reference + token | | | SHOULD	 | | &check;|
	

### MedicationDispense
   
    GET [base]/MedicationDispense?param1=value&...{&_format=[mime-type]}
 
UK Core Profile {{link:https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationDispense}}

Search Parameters [MedicationDispense](https://hl7.org/fhir/R4/MedicationDispense.html#search)

The following search parameter combinations should be supported:

| Parameters | Type | _include | Modifiers | Optionality| IHE QEDm |HL7 UK CORE ACCESS |
|--
| patient | reference | | | SHALL | | &check;|	 
| _id | token | | | SHOULD | | &check;|	
| patient + when-prepared | reference + date | | |SHOULD | | &check;|	
| patient + status | reference + token | | | SHOULD	 | | &check;|



