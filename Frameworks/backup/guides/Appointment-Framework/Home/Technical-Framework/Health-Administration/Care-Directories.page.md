## {{page-title}}

See also [HL7 FHIR Administration - Service Provider Directory Resources](http://hl7.org/fhir/R4/administration-module.html#dir-reg)

{{render:diagrams-Administration-administration-module-prov-dir}}

- [IHE Mobile Care Services Discovery (mCSD)](https://profiles.ihe.net/ITI/mCSD/index.html) The Mobile Care Services Discovery (mCSD) Profile supports RESTful queries across related care services resources.

The loosely coupled design and flexible querying capability of the mCSD Profile means it can be deployed within a variety of eHealth architectures and support a wide array of care workflows.


### Organization FHIR API

NHS England Profile {{link:https://fhir.nhs.uk/StructureDefinition/England-Organization}}

   
    GET [base]/Organization?param1=value&...{&_format=[mime-type]}
 

Search Parameters [Organization](https://hl7.org/fhir/R4/Organization.html#search)

The following search parameters should be supported:

| Parameters | Type | _include | Modifiers | Optionality | IHE mCSD | ODS STU3 |
|--
| active|  token |  | | SHALL | &check;| &check; |
| identifier|  token |  | | SHALL | &check;|&check; |
| name | string |  | | SHALL | &check;|&check; |
| partof |  reference |  | | SHALL | &check;|
| type | token |  | | SHALL | &check;| supports this as ods-org-role |
||reference| Organization.endpoint| SHALL | | &check;|
||reference| (reverse) Location:organization| SHALL | | &check;|
||reference| (reverse) OrganizationAffiliation :participating-organization| SHALL | | &check;|
||reference| (reverse) OrganizationAffiliation :primary-organization| SHALL | | &check;|


### Practitioner FHIR API

NHS England Profile {{link:https://fhir.nhs.uk/StructureDefinition/England-Practitioner}}

   
    GET [base]/Practitioner?param1=value&...{&_format=[mime-type]}
 

Search Parameters [Practitioner](https://hl7.org/fhir/R4/Practitioner.html#search)

The following search parameters should be supported:

| Parameters | Type | _include | Modifiers | Optionality | IHE mCSD | SDS |
|--
| active |  token |  | | SHALL | &check;| |
| identifier | token |  | | SHALL | &check;| |
| name| string |  | | SHALL | &check;| |
| given| string |  | | SHALL | &check;| |
| family| string |  | | SHALL | &check;| |


### PractitionerRole FHIR API

NHS England Profile {{link:https://fhir.nhs.uk/StructureDefinition/England-PractitionerRole}}
   
    GET [base]/PractitionerRole?param1=value&...{&_format=[mime-type]}
 
Search Parameters [PractitionerRole](https://hl7.org/fhir/R4/PractitionerRole.html#search)

The following search parameters should be supported:

| Parameters | Type | _include | Modifiers | Optionality | IHE mCSD | SDS |
|--
| active|  token |  | | SHALL | &check;| |
| location|  reference |  | | SHALL | &check;| |
| organization|  reference |  | | SHALL | &check;| |
| practitioner|  reference |  | | SHALL | &check;| |
| role|  token |  | | SHALL | &check;| |
| service|  reference |  | | SHALL | &check;| |
| specialty|  token |  | | SHALL | &check;| |
| | reference | PractitionerRole:practitioner| | SHALL | &check;| |

### HealthcareService FHIR API

NHS England Profile {{link:https://fhir.nhs.uk/StructureDefinition/England-HealthcareService}}
   
    GET [base]/HealthcareService?param1=value&...{&_format=[mime-type]}
 
Search Parameters [HealthcareService](https://hl7.org/fhir/R4/HealthcareService.html#search)

The following search parameters should be supported:

| Parameters | Type | _include | Modifiers | Optionality | IHE mCSD | DoS |
|--
| active|  token |  | | SHALL | &check;| |
| identifier|  token |  | | SHALL | &check;| |
| location|  reference |  | | SHALL | &check;| |
| name|  string |  | | SHALL | &check;| |
| organization|  reference |  | | SHALL | &check;| |
| service-type|  token |  | | SHALL | &check;| |

### Endpoint FHIR API

NHS England Profile {{link:https://fhir.nhs.uk/StructureDefinition/England-Endpoint}}
   
    GET [base]/Endpoint?param1=value&...{&_format=[mime-type]}
 
Search Parameters [Endpoint](https://hl7.org/fhir/R4/Endpoint.html#search)

The following search parameters should be supported:

| Parameters | Type | _include | Modifiers | Optionality | IHE mCSD | SDS |
|--
| identifier | token |  | | SHALL | &check;| &check; |
| organization| reference |  | | SHALL | &check;| supports organization:identifier as organization |
| status| token |  | | SHALL | &check;|  |


### OrganizationAffiliation FHIR API

No NHS England or UK Core Profile 

    GET [base]/OrganizationAffiliation?param1=value&...{&_format=[mime-type]}
 
Search Parameters [OrganizationAffiliation](https://hl7.org/fhir/R4/OrganizationAffiliation.html#search)

The following search parameters should be supported:

| Parameters | Type | _include | Modifiers | Optionality | IHE mCSD | ODS |
|--
| active | token |  | | SHALL | &check;|  |
| date |  date |  | | SHALL | &check;|  |
| identifier | token |  | | SHALL | &check;|  |
| participating-organization |  reference |  | | SHALL | &check;|  |
| primary-organization | reference |  | | SHALL | &check;|  |
| role |  token |  | | SHALL | &check;|  |
| | reference | OrganizationAffiliation .endpoint | | SHALL | &check;|  |

### Location FHIR API

NHS England Profile {{link:https://fhir.nhs.uk/StructureDefinition/England-Location}}

   
    GET [base]/Location?param1=value&...{&_format=[mime-type]}
 

Search Parameters [Location](https://hl7.org/fhir/R4/Location.html#search)

The following search parameters should be supported:

| Parameters | Type | _include | Modifiers | Optionality | IHE mCSD | 
|--
| identifier | token |  | | SHALL | &check;|
| name | string |  | | SHALL | &check; | 
| organization |  reference |  | | SHALL |&check; |
| partof | reference |  | | SHALL | &check;|
| status | token |  | | SHALL | &check;| 
| type | token |  | | SHALL | &check; | 
| | | Location:organization | | SHALL | &check; |
| near | | | | | 