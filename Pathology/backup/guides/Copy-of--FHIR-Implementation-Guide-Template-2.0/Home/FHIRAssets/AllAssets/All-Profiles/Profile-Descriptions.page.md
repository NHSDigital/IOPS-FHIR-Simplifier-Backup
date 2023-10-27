---
topic: ProfileDescriptions
---
## Profile Descriptions
This specification documents the use of FHIR UK Core R4 profiles to support the exchange of pathology laboratory data. Each profile is documented as follows:

### Summary
A brief description of the profile.

### Related Links
Links to the base FHIR resource and the associated profile.

### Profile Views
A formal definition of the profile presented using the following views:

* **Snapshot**: a full definition of the profile
* **Differential**: a description of the differences between the base FHIR resource and the associated profile
* **Hybrid**: a combination of the Snapshot and Differential views

### Additional Guidance
Additional guidance that should be followed when implementing the profile. The guidance is presented as a table with the following column headings:

* **Element Name**: the FHIR data element name or extension name
* **Profile Cardinality**: the cardinality that has been applied to the profile data element
* **Domain Cardinality**: the business or domain level cardinality that has been applied to the data element; this may differ from the profile cardinality definition e.g. the profile may state 0..1 but the required domain level cardinality is `1..1` and is indicated accordingly
* **Domain Optionality**: this is populated with one of the following values:
  * Mandatory: the data element must always be populated
  * Required: the data element must be populated if the associated data is available
  * Optional: the data element may be left unpopulated
* **Definition, Constraints and Notes**: used to clarify how data elements should be populated or to define any constraints that should be applied in addition to those specified by the profile