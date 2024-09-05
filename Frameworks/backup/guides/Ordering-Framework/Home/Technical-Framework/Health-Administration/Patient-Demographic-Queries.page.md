## {{page-title}}

- [Patient Demographics Query for Mobile (PDQm)](https://profiles.ihe.net/ITI/PDQm/index.html)
- [Personal Demographics Service - FHIR API](https://digital.nhs.uk/developer/api-catalogue/personal-demographics-service-fhir)


### Patient FHIR API

NHS England Profile {{link:https://fhir.nhs.uk/StructureDefinition/England-Patient}}

   
    GET [base]/Patient?param1=value&...{&_format=[mime-type]}
 

Search Parameters [Patient](https://hl7.org/fhir/R4/Patient.html#search)

The following search parameters should be supported:

| Parameters | Type |Modifiers | Optionality | IHE PDQm | PDS |
|--
| _id |	string	| |  SHALL |&check; | |
| active |	token	| |  SHALL |&check; | |
| family |	string	| |  SHALL |&check; | &check;|
| given |	string	| |  SHALL |&check; | &check;|
| identifier |	token	| |  SHALL |&check; | |
| telecom |	string	| |  SHALL |&check; | Supports email and phohe |
| birthdate |	string	| |  SHALL |&check; | &check;|
| address |	string	| |  SHALL |&check; | |
| address-city |	string	| |  SHALL |&check; | |
| address-country |	string	| |  SHALL |&check; | |
| address-postalcode |	string	| |  SHALL |&check; | &check;|
| address-state |	string	| |  SHALL |&check; | |
| gender |	token	| |  SHALL |&check; | &check;|
| mothersMaidenName |	string	| |  SHALL |&check; | |