## `dosageInstruction`

<b>Definition</b><br>

The content of the `dosageInstruction` should follow guidance in [Digital Medicines Dosage](https://simplifier.net/guide/ukcoreimplementationguideformedicines/ElementDosage).


`dosageInstruction.text` **MUST** be supplied and is a human readable version of the structured dose as would be printed on a paper prescription. The use of a generic default value, for example “Use as directed”, if a value is not entered, is not acceptable from a clinical perspective. The user must be asked to select a dosage instruction from a pick list, type by hand or have the system populate with a valid and clinically safe dosage instruction relevant to the prescribed medication or clinical circumstances.

As per BNF guidelines, the dosage must be presented to the user without abbreviation although it may be entered and stored within the PMR in an abbreviated form. Within HL7 messaging, the dosage instruction must be represented without abbreviation.

### `dosageInstruction.additionalInstruction`

These sections **MUST** be used only be used to pass notes regarding the prescription to the pharmacist or patient. Lists of repeat medications and general practice notifications to the patient **SHOULD** be recorded in CommunicationRequest resource.

Patient instructions for taking the drug are contained with in the `patientInstruction` and `additionalInstruction` as per the guidance in [Dosage Structure Overview](https://developer.nhs.uk/apis/dose-syntax-implementation/dosage-overview.html).

### `dosageInstruction.patientInstruction`

These sections **MUST** be used only be used to pass notes regarding the prescription to the pharmacist or patient. Lists of repeat medications and general practice notifications to the patient **SHOULD** be recorded in CommunicationRequest resource

Patient instructions for taking the drug are contained with in the `patientInstruction` and `additionalInstruction` as per the guidance in [Dosage Structure Overview](https://developer.nhs.uk/apis/dose-syntax-implementation/dosage-overview.html).

---