## Dispensing

<br>

The prescribed medication items on a prescription may not be fulfilled in one dispensing event. Each time medication is supplied to a patient, a dispense notification message must be submitted.

For items that are owing, the `MedicationDispense` is recorded without the following elements 

- performer
- quantity
- daysSupply
- whenPrepared
- dosageInstruction 

as nothing as being supplied, and an item status of “Item not dispensed – owing” (0004).

For items that are partially dispensed, the `MedicationDispense` is recorded with the quantity of medication dispensed and an item status of “Item dispensed - partial” (0003).

When further medication items are dispensed in a separate dispensing event, another dispense notification message is submitted. This process is repeated until all medication items are dispensed.

Note. The coded medication information contained within the Dispense Notification should reflect the actual medication supplied to the patient. This information will, in time, form part of the patient’s national medication record but is not used by the NHS BSA as part of prescription reimbursement calculations.

{{render:epsPatientDispensingandOwings}}

The following table details how a prescription for the quantity of 100 Paracetamol tablets and single Salbutamol inhaler would be recorded in dispense notification messages if the tablets were dispensed over three separate dispensing events and the inhaler dispensed during the first dispensing event

#### Prescribing Event 

{{render:process-message-duplicate-2}}

This is the initial (GP) prescription sent by the prescriber using the FHIR Operation {{pagelink:process-message-duplicate-3}} with an example payload:
{{pagelink:PrescriptionOrderGPwithpatientnotes-duplicate-2}}

| Medication ID (SNOMED) | Medication Name | Prescribed Quantity | Unit of Measure |
|--
| 322237000 | Paracetamol 500mg soluble tablets | 100 | Tablet |
| 35936511000001108 | Salbutamol 100micrograms/dose inhaler | 200 | Dose |

The notes consist of a list of repeat medications

| Medication Name |
|--
| Bendroflumethiazide 2.5 mg Tablets (3/6) |
| Salbutamol 100micrograms/dose inhaler CFC free 200 dose (2/6) |

plus a note to the patient. 

| Patient Notes |
|--
| Due to Coronavirus restrictions Church View Surgery is CLOSED until further notice | 
