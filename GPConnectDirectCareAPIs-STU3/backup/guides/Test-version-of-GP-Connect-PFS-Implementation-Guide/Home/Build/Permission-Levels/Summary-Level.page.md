## {{page-title}}

At Summary level a patient only has access to their Demographics, Medication and Allergy sections of their record. 

Therefore at this stage, as more than this is stored on the GP systems record the provider must ensure that anything else on the patient's record (Immunizations, Health Conditions, Test results, Consultations, Referrals, Documents are NOT returned as part of the response).

Following that means that the provider MUST reject any request for other parts of the record from consumers that does not align with the patients permission level. 

For example if the patient only has summary access, however the providing system receives a request in error from the consumer for health conditions and referrals this must be rejected.

At this access level, the only resources eligible to be surfaced by the request are: `Patient`, `Organization`, `Practitioner`, `PractitionerRole`, `Medication`, `MedicationStatement`, `MedicationRequest` and `AllergyIntolerance`.

Any linked references that are a resource not listed above MUST not be included in the response.