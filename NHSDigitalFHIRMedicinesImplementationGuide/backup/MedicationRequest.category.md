### MedicationRequest.category

This is optional in UKCore R4 and CareConnect STU3, it is **required** in NHS Digital Medicines. In NHS Digital Medicines this is a code from `https://fhir.nhs.uk/ValueSet/DM-medicationrequest-category`. Primary care prescriptions should use a `community` code. Secondary care should match the EpisodeOfCare/Encounter class (or Patient Class Table 0004 in HL7 v2).

{{render:https://fhir.nhs.uk/ValueSet/DM-medicationrequest-category}}