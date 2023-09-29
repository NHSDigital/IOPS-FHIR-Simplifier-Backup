## {{page-title}}

Clinical items linked to a consultation, contain a reference to a FHIR resource, which is held in the `entry.item` field in the apporpriate `List` resource.

- A planned prescription with a medication or medical device can be represented with the `CareConnect-GPC-MedicationRequest-1` profile, with the `intent` element, containing the value of `plan`
- An issued prescription with a medication or medical device can be represented with the `CareConnect-GPC-MedicationRequest-1` profile, with the `intent` element, containing the value of `order`
- An allergy can be represented with the `CareConnect-AllergyIntolerance-1` profile
- An immunisation can be referenced with the `CareConnect-GPC-Immunization-1` profile
- Uncategorised data can be represented with the `CareConnect-GPC-Observation-1` profile
- A referral can be represented with the `CareConnect-GPC-ReferralRequest-1` profile
- A document can be represented with the `CareConnect-GPC-DocumentReference-1` profile
- An investigation can be represented with the `CareConnect-GPC-DiagnosticReport-1` profile
- A diary entry can be represented with the `CareConnect-GPC-ProcedureRequest-1` profile

---