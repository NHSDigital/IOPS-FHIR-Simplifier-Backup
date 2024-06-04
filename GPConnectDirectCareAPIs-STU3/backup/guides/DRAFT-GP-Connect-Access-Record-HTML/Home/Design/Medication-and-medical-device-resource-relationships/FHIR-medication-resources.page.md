## {{page-title}}

FHIR has a collection of resources that are available to represent different concepts related to medications and medical devices. These resources are intended to cover the full medication lifecycle:

|Resource name|Description|Used in GP Connect|
|---|---|---|
| [Medication](https://simplifier.net/guide/gpconnect-data-model/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-GPC-Medication-1?version=current) | The actual medication or medical device. | Yes |
| [MedicationRequest](https://simplifier.net/guide/gpconnect-data-model/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-GPC-MedicationRequest-1?version=current) |Planning, proposing or ordering medications or medical devices. | Yes |
| [MedicationStatement](https://simplifier.net/guide/gpconnect-data-model/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-GPC-MedicationStatement-1?version=current) | Used to make a statement about the medication or medical device a person has taken and can be ‘basedOn’ a record of an historic prescription that would be represented using one or more MedicationRequest resources. | Yes |
| [MedicationDispense](https://simplifier.net/guide/gpconnect-data-model/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-GPC-MedicationDispense-1?version=current) | Represent exactly what medication/medical device was dispensed. In some cases, this can differ slightly from what was ordered/prescribed. | No |
| `MedicationAdministration` |Describe when the medication/medical device is administered, how it was given and by whom. | No |

In GP Connect, we are interested in the medication and medical device data that is captured in GP clinical systems. This data is about the practice’s record of medications/medical devices that the patient has taken and whether they has been prescribed by a clinician at that practice.

Therefore, as shown in the table above, in order be able to represent the information that is available in the GP systems we are interested in three of the above FHIR profiles: `Medication`, `MedicationRequest` and `MedicationStatement`.