## `authorizingPrescription`

<b>Definition:</b><br>

A reference to the MedicationRequest.

When a MedicationDispesne is sent in a FHIR Message bundle, which is the case with EPS NextGen dispense-notifications, a contained MedicationRequest is required.

This MedicationRequest MUST follow the rules in England-MedicationRequest and it is strongly recommended to reuse the MedicationRequest received when the prescription was downloaded.

This is based on a MedicationRequest in this implementation guide. The uuid resource references are not permitted and must be replaced with identifier references. 

---


