## `medication[x]` (Mandatory)

This is a mandatory element and is recommended to be used to represent the medication that was supplied - even if it differs to the original `MedicationRequest`.

Where the dispensed medication is contained within the [NHS dm+d](https://www.nhsbsa.nhs.uk/pharmacies-gp-practices-and-appliance-contractors/dictionary-medicines-and-devices-dmd) then it must be recorded using the dm+d standard.

When referencing a `Medication` resource, it is recommended that the `medicationReference.display` is populated with the medication description as selected by the clinician. This may be slightly different to the medication described as returned by a SNOMED/dm+d terminology FHIR server if the dispensing system has not fully implemented dm+d into their medication picking list.

### Requested medication with no dm+d code

Medication not published within the dm+d may be dispensed in the Acute care setting. 

In this scenario it is recommended to use the `CodeableConcept` variant for this element. Software logic can then clearly distinguish this from nationally coded dm+d medication.

If the dispensing system has both a locally assigned code and description for the medication then;

- The `medicationCodeableConcept.text` should be the description for the medication.
- The `medicationCodeableConcept.coding.code` should be the code for the medication.
- The `medicationCodeableConcept.coding.display` should be the description for the medication, i.e. the same value as `medicationCodeableConcept.text`.

If the dispensing system only has a description for the medication then;

- The` medicationCodeableConcept.text` should be the locally assigned description for the medication.

### Multiple dispense requests for a single medication request

In the event that multiple dispense requests are required to fulfil a `MedicationRequest`, the same requesting `identifier` should be used with the appropriate `status`.

An example of this could be the Cosopt medication where one medication request would be received; however, two dispense messages would be returned for Dorzolamide and Timolol.

---
