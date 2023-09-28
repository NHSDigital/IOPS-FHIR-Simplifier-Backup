## `medication[x]`

<div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-information"></i><h4>Important:</h4>
Rules for determining the value of this element when constructing the resource from other FHIR resources.
</div>

### When only a `MedicationRequest` is <u>known</u>

**Rule**: Use the medication defined within the `basedOn` (MedicationRequest).

### When only a `MedicationDispense` is <u>known</u>

**Rule**: Use the medication defined within the `partOf` (MedicationDispense).

### When both the `MedicationRequest` and `MedicationDispense` are <u>known</u>

**Rule**: Where different dm+d concepts are used within the `basedOn` (MedicationRequest) and `partOf` (MedicationDispense) use the medication defined within the `partOf` (MedicationDispense).

The dispensing record will be the most specific and accurate for what will be given to the patient.

Also note that the `dosageInstruction` within a `MedicationDispense` may differ from that stated in the `MedicationRequest`. The pharmacy team may have applied their own dosage instruction to make it more suitable for a medicines administration label.

### When both the `MedicationRequest` or `MedicationDispense` are <u>not known</u>

**Rule**: Use the medication information available within the source clinical system.

### Populating the Element

Where a dm+d code exists it **MUST** be used either as `CodeableConcept.coding` or as `Medication.Medication.code`.

Where CodeableConcept is used, `CodeableConcept.coding` is the dm+d code and `CodeableConcept.text` is dm+d concept name/description. Where no dm+d code is available the drug name can be provided as text within the `CodeableConcept.text`

Can be either a dm+d code as a CodeableConcept or reference to UK Core `Medication` resource. Using a CodeableConcept is preferred unless additional data if required that would be contained within a UK Core `Medication` resource.

Examples where a reference to a UK Core `Medication` would be applicable include:

- Record a VTM with a specific form 
- Record manufacturer with a VTM, VMP or VMP concept
- Record batch number
- Record ingredients (for example with a magisterial prescription or an excipient). 

---
