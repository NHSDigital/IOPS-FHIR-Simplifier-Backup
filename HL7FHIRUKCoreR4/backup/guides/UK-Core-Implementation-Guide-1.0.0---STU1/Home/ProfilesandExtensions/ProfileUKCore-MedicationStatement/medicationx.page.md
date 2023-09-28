## `medication[x]`

<div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-information"></i><h4>Important:</h4>
Rules for determining the value of this element when constructing the resource from other FHIR resources.

### When only a `MedicationRequest` is <u>available</u>

**Rule:** Use the medication defined within the `MedicationStatement.basedOn.reference: MedicationRequest.medication[x]` 

### When only a `MedicationDispense` is <u>available</u>

**Rule:** Use the medication defined within the `MedicationStatement.partOf.reference:MedicationDispense.medication[x]`.

### When both the `MedicationRequest` and `MedicationDispense` are <u>available</u>

**Rule:** Where different dm+d concepts are used within the `MedicationStatement.basedOn.reference:MedicationRequest.medication[x]` and `MedicationDispense.partOf.reference:MedicationDispense.medication[x]`, use the medication defined within the `MedicationStatement.partOf.reference:MedicationDispense.medication[x]`.

The dispensing record will be the most specific and accurate for what will be given to the patient.

Also note that the `MedicationDispense.dosageInstruction` may differ from that stated in the `MedicationRequest.dosageInstruction`. The pharmacy team may have applied their own dosage instruction to make it more suitable for a medicine's administration label.

### When both the `MedicationRequest` and `MedicationDispense` are <u>not available</u>

**Rule:** Use the medication information available within the source clinical system.
</div>

### Medication WITH dm+d code

Where a dm+d code exists it SHALL be used either as `MedicationStatement.medicationCodeableConcept.coding` or as `MedicationStatement.medicationReference:Medication.code`.

Where CodeableConcept is used, `MedicationStatement.medicationCodeableConcept.coding` is the dm+d code and `MedicationStatement.medicationCodeableConcept.text` is dm+d concept name/description. 

Can be either a dm+d code as a CodeableConcept or reference to {{pagelink:Profile-Medication-c9b14f01-2a2e-479a-b71e-094d2a882605}}
 resource. Using a CodeableConcept is preferred unless additional data if required that would be contained within a {{pagelink:Profile-Medication-c9b14f01-2a2e-479a-b71e-094d2a882605}} resource.

The elements `MedicationStatement.medicationCodeableConcept.coding` and `MedicationStatement.medicationReference:Medication.code` are both bound to {{pagelink:ValueSet-UKCore-MedicationCode}}

Examples where a reference to a {{pagelink:Profile-Medication-c9b14f01-2a2e-479a-b71e-094d2a882605}} would be applicable include:

- Record a VTM with a specific form 
- Record manufacturer with a concept as described in {{pagelink:ValueSet-UKCore-MedicationCode}}
- Record batch number
- Record ingredients (for example with a magisterial prescription or an excipient). 

### Medication WITHOUT dm+d code

Medication not published within the dm+d may be requested in the Acute care setting.

In this scenario it is recommended to use the CodeableConcept variant for this element. 

If the prescribing system has both a locally assigned code and description for the medication then;

- The `MedicationStatement.medicationCodeableConcept.text` SHOULD be the description for the medication.  
- The `MedicationStatement.medicationCodeableConcept.coding.code` SHOULD be the code for the medication.  
- The `MedicationStatement.medicationCodeableConcept.coding.display` SHOULD be the description for the medication, i.e. the same value as `MedicationStatement.medicationCodeableConcept.text`.  

If the prescribing system only has a description for the medication then;  

- The `MedicationStatement.medicationCodeableConcept.text` SHOULD be the locally assigned description for the medication.  

---
