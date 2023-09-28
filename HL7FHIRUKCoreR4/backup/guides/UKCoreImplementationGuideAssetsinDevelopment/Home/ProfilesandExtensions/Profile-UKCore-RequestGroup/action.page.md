## `{{page-title}}`

With the base FHIR constraint rule *"Must have resource or action but not both"* it is expected that:
- `RequestGroup.action` has multiple `action` elements, each defining an individual MedicationRequest. 
- Within each of the `Medication.action.action` the `resource` element SHOULD reference the associated `MedicationRequest`.

 ### `action.participant`

The resource being referenced SHALL conform to one of the following:

- UKCore-Patient
- UKCore-Practitioner
- UKCore-PractitionerRole
- UKCore-RelatedPerson
- UKCore-Device
<!--
- {{pagelink:Profile-Patient}}
- {{pagelink:Profile-Practitioner}}
- {{pagelink:Profile-PractitionerRole}}
- {{pagelink:Profile-RelatedPerson}}
- {{pagelink:Profile-Device}}
-->

---
