## `medication[x]`  (Mandatory)

Where a dm+d code exists it **MUST** be used either as `CodeableConcept.coding` or as `Medication.Medication.code`

Where CodeableConcept is used, `CodeableConcept.coding` is the dm+d code and `CodeableConcept.text` is dm+d concept name/description. Where no dm+d code is available the drug name can be provided as text within the `CodeableConcept.text`

Can be either a dm+d code as a CodeableConcept or reference to UK Core `Medication` resource. Using a CodeableConcept is preferred unless additional data if required that would be contained within a UK Core `Medication` resource.

Examples where a reference to a UK Core `Medication` would be applicable include:

- Record a VTM with a specific form 
- Record manufacturer with a VTM, VMP or VMP concept
- Record batch number
- Record ingredients (for example with a magisterial prescription or an excipient). 

---
