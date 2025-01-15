## {{page-title}}



### DocumentReference - Get Document List

UK Core Profile {{link:https://fhir.hl7.org.uk/StructureDefinition/UKCore-DocumentReference}}

   
    GET [base]/DocumentReference?param1=value&...{&_format=[mime-type]}
 

Search Parameters [DocumentReference](https://hl7.org/fhir/R4/DocumentReference.html#search)

All searches shall use search combinations and include the following :

| Parameters | Type |Modifiers | Optionality | IHE MHD | NRL |
|--
| patient |	reference	| |  SHALL |&check; | |
| patient.identifier | reference  | | SHALL |&check; | |
| subject:identifier | token  | | SHALL | | &check; |

All searches should use the following parameters:

| Parameters | Type |Modifiers | Optionality | IHE MHD | NRL |
|--
|  author.given |	string	| |  SHOULD |&check; | |
|  author.family |	string	| |  SHOULD |&check; | |
|  category |	token	| |  SHOULD |&check; | |
|  creation |	date	| |  SHOULD |&check; | |
|  date |	date	| |  SHOULD |&check; | |
|  event |	token	| |  SHOULD |&check; | |
|  facility |	token	| |  SHOULD |&check; | |
|  format |	token	| |  SHOULD |&check; | |
|  identifier |	token	| |  SHOULD |&check; | |
|  period |	date	| |  SHOULD |&check; | |
|  related |	date	| |  SHOULD |&check; | |
|  security-label |	token	| |  SHOULD |&check; | |
|  setting |	token	| |  SHOULD |&check; | |
|  status |	token	| |  SHOULD |&check; | |
|  type |	token	| |  SHOULD |&check; |&check; |

