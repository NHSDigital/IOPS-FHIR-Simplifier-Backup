## `{{page-title}}`

With the base FHIR constraint rule *"Must have resource or action but not both"* it is expected that:
- `RequestGroup.action` has multiple `action` elements, each defining an individual MedicationRequest. 
- Within each of the `Medication.action.action` the `resource` element SHOULD reference the associated `MedicationRequest`.

 ### `action.participant`

The resource being referenced SHALL conform to one of the following:

- {{pagelink:Profile-Device}}
- [Profile UKCore-Patient](https://simplifier.net/guide/UK-Core-Implementation-Guide-STU3-Sequence/Home/ProfilesandExtensions/Profile-UKCore-Patient)
- [Profile UKCore-Practitioner](https://simplifier.net/guide/UK-Core-Implementation-Guide-STU3-Sequence/Home/ProfilesandExtensions/Profile-UKCore-Practitioner)
- [Profile UKCore-PractitionerRole](https://simplifier.net/guide/UK-Core-Implementation-Guide-STU3-Sequence/Home/ProfilesandExtensions/Profile-UKCore-PractitionerRole)
- [Profile UKCore-RelatedPerson](https://simplifier.net/guide/UK-Core-Implementation-Guide-STU3-Sequence/Home/ProfilesandExtensions/Profile-UKCore-RelatedPerson)


---
