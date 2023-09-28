## `identifier`

The organisation ODS code and optionally the ODS site code for a specific site in the oranisation

### Organisation


**Organization.identifier:odsOrganisationCode.use**

usual | official | temp | secondary | old (If known)

**Organization.identifier:odsOrganisationCode.type**

Not required for use with ODS

**Organization.identifier:odsOrganisationCode.system**

The url is `https://fhir.nhs.uk/Id/ods-organization-code`

**Organization.identifier:odsOrganisationCode.value**

The ODS code

**Organization.identifier:odsOrganisationCode.period**

The period for which the code is valid - May be ommitted

**Organization.identifier:odsOrganisationCode.assigner**

Implicit for ODS codes - Should be ommitted 

### Site

**Organization.identifier:odsSiteCode.use**
 
usual | official | temp | secondary | old (If known)
 
**Organization.identifier:odsSiteCode.type**
 
Not required for use with ODS
 
**Organization.identifier:odsSiteCode.system**
 
The url is `https://fhir.nhs.uk/Id/ods-site-code`
 
**Organization.identifier:odsSiteCode.value**
 
The ODS site code
 
**Organization.identifier:odsSiteCode.period**
 
The period for which the code is valid - May be omitted
 
**Organization.identifier:odsSiteCode.assigner**
 
Implicit for ODS site codes - Should be omitted
