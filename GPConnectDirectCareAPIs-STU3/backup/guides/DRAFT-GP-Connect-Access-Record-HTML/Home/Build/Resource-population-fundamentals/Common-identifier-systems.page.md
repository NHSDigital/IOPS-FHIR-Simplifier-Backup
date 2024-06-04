## {{page-title}}

The following common identifier systems are used when populating `Identifier.system` in resources for this capability:

| Name                                                             | Identifier system                                       |
| ----                                                             | -----------------                                       |
| NHS number                                                       | `https://fhir.nhs.uk/Id/nhs-number`                     |
| ODS organisation code                                            | `https://fhir.nhs.uk/Id/ods-organization-code`          |
| ODS site code                                                    | `https://fhir.nhs.uk/Id/ods-site-code`                  |
| SDS user ID                                                      | `https://fhir.nhs.uk/Id/sds-user-id`                    |
| SDS role profile ID                                              | `https://fhir.nhs.uk/Id/sds-role-profile-id`            |
| General Medical Council (GMC) number                             | `https://fhir.hl7.org.uk/Id/gmc-number`                 |
| General Practitioner (GMP) number                                | `https://fhir.hl7.org.uk/Id/gmp-number`                 |
| EPS prescription order item identifier                           | `https://fhir.nhs.uk/Id/prescription-order-item-number` |
| EPS short form prescription identifier                           | `https://fhir.nhs.uk/Id/prescription-order-number`      |
| e-Referral Service (e-RS) Unique Booking Reference Number (UBRN) | `https://fhir.nhs.uk/Id/UBRN`                           |

The following profiled <span class="stu3">STU3</span> FHIR&reg; resources are used in this capability pack:

### Business identifiers for resources

Each clinical resource will have a unique business identifier that will be persisted to help consuming systems distinguish data they have integrated previously to data which is new to them. These identifiers will be scoped by a supplier specific namespace to ensure uniqueness.

### Clinical ###

- [AllergyIntolerance](https://simplifier.net/guide/gpconnect-data-model/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-GPC-AllergyIntolerance-1?version=current)
- [Medication](https://simplifier.net/guide/gpconnect-data-model/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-GPC-Medication-1?version=current)
- [MedicationStatement](https://simplifier.net/guide/gpconnect-data-model/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-GPC-MedicationStatement-1?version=current)
- [MedicationRequest](https://simplifier.net/guide/gpconnect-data-model/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-GPC-MedicationRequest-1?version=current)
- [Immunization](https://simplifier.net/guide/gpconnect-data-model/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-GPC-Immunization-1?version=current)
- [Observation - uncategorised data](https://simplifier.net/guide/gpconnect-data-model/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-GPC-Observation-1?version=current)
- [Observation - blood pressure](https://simplifier.net/guide/gpconnect-data-model/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-GPC-Observation-1?version=current)
- [Encounter](https://simplifier.net/guide/gpconnect-data-model/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-GPC-Encounter-1?version=current)
- [List - consultation structure](https://simplifier.net/guide/gpconnect-data-model/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-GPC-List-1?version=current)
- [Observation - narrative data](https://simplifier.net/guide/gpconnect-data-model/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-GPC-Observation-1?version=current)
- [Condition - ProblemHeader](https://simplifier.net/guide/gpconnect-data-model/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-GPC-ProblemHeader-Condition-1?version=current)
- [Diagnostic Report](https://simplifier.net/guide/gpconnect-data-model/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-GPC-DiagnosticReport-1?version=current)
- [Specimen](https://simplifier.net/guide/gpconnect-data-model/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-GPC-Specimen-1?version=current)
- [Observation - Test Group Header](https://simplifier.net/guide/gpconnect-data-model/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-GPC-Observation-1?version=current)
- [Observation - Test Result](https://simplifier.net/guide/gpconnect-data-model/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-GPC-Observation-1?version=current)
- [Observation - Filing Comments](https://simplifier.net/guide/gpconnect-data-model/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-GPC-Observation-1?version=current)
- [ProcedureRequest](https://simplifier.net/guide/gpconnect-data-model/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-GPC-ProcedureRequest-1?version=current)
- [ReferralRequest](https://simplifier.net/guide/gpconnect-data-model/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-GPC-ReferralRequest-1?version=current)
- [ProcedureRequest - Diary Entry](https://simplifier.net/guide/gpconnect-data-model/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-GPC-ProcedureRequest-1?version=current)
- [DocumentReference](https://simplifier.net/guide/gpconnect-data-model/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-GPC-DocumentReference-1?version=current)

### Administrative ###

- [HealthcareService](https://simplifier.net/guide/hl7fhircareconnectprofilesstu3/Home/ProfilesandExtensions/AllAssets/AllProfiles/ProfileCareConnect-HealthcareService.guide.md?version=current)
- [Location](https://simplifier.net/guide/gpconnect-data-model/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-GPC-Location-1?version=current)
- [Organization](https://simplifier.net/guide/gpconnect-data-model/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-GPC-Organization-1?version=current)
- [Patient](https://simplifier.net/guide/gpconnect-data-model/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-GPC-Patient-1?version=current)
- [Practitioner](https://simplifier.net/guide/gpconnect-data-model/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-GPC-Practitioner-1?version=current)
- [PractitionerRole](https://simplifier.net/guide/gpconnect-data-model/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-GPC-PractitionerRole-1?version=current)

### Structural ###

- [Bundle](https://simplifier.net/guide/gpconnect-data-model/Home/FHIR-Assets/All-assets/Profiles/Profile--GPConnect-Searchset-Bundle-1?version=current)
- [List](https://simplifier.net/guide/gpconnect-data-model/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-GPC-List-1?version=current)