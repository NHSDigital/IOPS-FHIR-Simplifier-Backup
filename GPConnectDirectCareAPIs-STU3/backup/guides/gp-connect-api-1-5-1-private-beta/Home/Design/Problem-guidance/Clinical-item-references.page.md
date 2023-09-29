## {{page-title}}

When a clinical item is linked to the problem, a reference to its FHIR® resource is held in either extension[actualProblem] or extension[relatedClinicalContent].

When linking to the clinical item that is held in a single FHIR resource the reference will be to that resource. When linking to the clinical item that is held across multiple resources (for example, Medication and Medical Device) the reference must be to the FHIR resource specified below.

- for a Medication or Medical Device prescription plan - reference the `MedicationRequest` (intent = plan) profile
- for a Medication or Medical Device prescription issue - reference the `MedicationRequest` (intent = order) profile
- for an Allergy – reference the `AllergyIntolerance` profile
- for a Consultation - reference the `Encounter` profile
- for an Immunisation – reference the `Immunization` profile
- for Uncategorised Data – reference the `Observation` – Uncategorised profile
- for a Referral - reference the `ReferralRequest` profile
- for a Document - reference the `DocumentReference` profile
- for an Investigation - reference the `DiagnosticReport` profile - if any item related to a diagnostic report is flagged as a problem the diagnostic report **MUST** be linked to the problem as a related clinical item
- for a Diary Entry - reference the `ProcedureRequest` profile

---