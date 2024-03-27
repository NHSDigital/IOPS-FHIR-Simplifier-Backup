## {{page-title}}

Clinical items linked to a consultation, contain a reference to a FHIR resource, which is held in the `entry.item` field in the apporpriate [CareConnect-GPC-List-1](https://simplifier.net/guide/gpconnect-data-model/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-GPC-List-1?version=current) resource.

- A planned prescription with a medication or medical device can be represented with the [CareConnect-GPC-MedicationRequest-1](https://simplifier.net/guide/gpconnect-data-model/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-GPC-MedicationRequest-1?version=current) profile, with the `intent` element, containing the value of `plan`
- An issued prescription with a medication or medical device can be represented with the [CareConnect-GPC-MedicationRequest-1](https://simplifier.net/guide/gpconnect-data-model/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-GPC-MedicationRequest-1?version=current) profile, with the `intent` element, containing the value of `order`
- An allergy can be represented with the [CareConnect-AllergyIntolerance-1](https://simplifier.net/guide/gpconnect-data-model/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-GPC-AllergyIntolerance-1?version=current) profile
- An immunisation can be referenced with the [CareConnect-GPC-Immunization-1](https://simplifier.net/guide/gpconnect-data-model/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-GPC-Immunization-1?version=current) profile
- Uncategorised data can be represented with the [CareConnect-GPC-Observation-1](https://simplifier.net/guide/gpconnect-data-model/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-GPC-Observation-1?version=current) profile
- A referral can be represented with the [CareConnect-GPC-ReferralRequest-1](https://simplifier.net/guide/gpconnect-data-model/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-GPC-ReferralRequest-1?version=current) profile
- A document can be represented with the [CareConnect-GPC-DocumentReference-1](https://simplifier.net/guide/gpconnect-data-model/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-GPC-DocumentReference-1?version=current) profile
- An investigation can be represented with the [CareConnect-GPC-DiagnosticReport-1](https://simplifier.net/guide/gpconnect-data-model/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-GPC-DiagnosticReport-1?version=current) profile
- A diary entry can be represented with the [CareConnect-GPC-ProcedureRequest-1](https://simplifier.net/guide/gpconnect-data-model/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-GPC-ProcedureRequest-1?version=current) profile

---