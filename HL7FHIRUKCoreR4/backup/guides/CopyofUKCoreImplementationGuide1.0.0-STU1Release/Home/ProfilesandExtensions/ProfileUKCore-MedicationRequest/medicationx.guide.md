## `medication`

Where the requested medication is contained within the [NHS dm+d](https://www.nhsbsa.nhs.uk/pharmacies-gp-practices-and-appliance-contractors/dictionary-medicines-and-devices-dmd) then it must be recorded using the dm+d standard.

When referencing a `Medication` resource, it is recommended that the `medicationReference.display` is populated with the medication description as selected by the clinician. This may be slightly different to the medication described as returned by a SNOMED/dm+d terminology FHIR server if the prescribing system has not fully implemented dm+d into their medication picking list.

### Requested medication with no dm+d code

Medication not published within the dm+d may be requested in the Acute care setting. 

In this scenario it is recommended to use the `CodeableConcept` variant for this element. Software logic can then clearly distinguish this from nationally coded dm+d medication.

If the prescribing system has both a locally assigned code and description for the medication then;

- The `medicationCodeableConcept.text` should be the description for the medication.
- The `medicationCodeableConcept.coding.code` should be the code for the medication.
- The `medicationCodeableConcept.coding.display` should be the description for the medication, i.e. the same value as `medicationCodeableConcept.text`.

If the prescribing system only has a description for the medication then;

- The` medicationCodeableConcept.text` should be the locally assigned description for the medication.

---
