### Prescription Cancellations

{{render:EPSCancelDiagram}}


#### 1. Prescriber - Send Prescription


This is sent to FHIR Operation {{pagelink:process-message}} as a 
{{pagelink:prescription-order}} Message.

The example outpatient prescription {{pagelink:PrescriptionOrderOutpatientMultipleMedications}} consists of four Medications and has nominated pharmacy `FX478` 


| Medication ID (SNOMED) | Medication Name | Prescribed Quantity | Unit of Measure |
|--
| 321196004 | Diazepam 2mg tablets | 28 | Tablet |
| 322236009 | Paracetamol 500mg tablets | 100 | Tablet |
| 321152004 | Temazepam 10mg tablets | 14 | Tablet |
| 36126511000001106 | Morphine 10mg modified-release tablets | 28 | Tablet |

<br>

#### 2. Dispenser - Release Prescription.


The Pharmacy releases the prescription by calling the FHIR Operation {{pagelink:release-duplicate-2}}

`POST /Task/$release`

Example of the payload {{pagelink:NominatedPharmacyReleaseRequestFX478.md}}

<br>

#### 3. Prescriber - Prescription MedicationRequest Cancellation

An electronic prescription MedicationRequest can be cancelled after submission to EPS provided the prescription has not been downloaded or processed by a dispenser.

To cancel a prescription the prescribing system is required to send a {{pagelink:prescription-order-update}} 
cancellation message to the FHIR Operation {{pagelink:process-message}}. 
A cancellation is at individual item level. Cancellation is applicable to all types of electronic prescriptions (i.e. acute, continuous prescribing and continuous dispensing prescriptions).

Example cancellation message {{pagelink:PrescriptionOrderOutpatientCancel.md}} which cancels the Morphine medication.

| Medication ID (SNOMED) | Medication Name | Prescribed Quantity | Unit of Measure |
|--
| 36126511000001106 | Morphine 10mg modified-release tablets | 28 | Tablet |

Note: this prescription is being cancelled by a clerical worker and the original prescriber is now down as the responsible party.

<br>

#### 4. Prescriber - Prescription Cancellation Response

The immediate response to a cancellation messge is a {{pagelink: prescription-order-response.md}} FHIR Message.
Example message {{pagelink:PrescriptionOrderOutpatientResponse}}

<br>

#### 5 Prescriber - Contact Pharmacy

Prescriptions sent to a nominated pharmacy are likely to be collected before they have been cancelled. This has happened in the above example and the prescriber **SHOULD** contact the pharmacy to cancel the prescription.

<br>

#### 6 Dispenser - Dispense Proposal Withdrawal

As no Medications have been dispensed, the pharmacy can return the entire prescription back to EPS. This is performed sending a FHIR Task to EPS Task endpoint. Note the full prescription must be returned to allow a single MedicationRequest to be cancelled.

`PUT /Task`

Example payload {{pagelink:TaskReturnPrescriptionOrder}}

<br>

#### 7 Prescriber - Subsequent Cancellation Response

As the prescription has now been returned to EPS, EPS can now send a {{pagelink: prescription-order-response.md}} message to the prescriber. This is sent via MESH and example payload:  
{{pagelink: PrescriptionOrderOutpatientSubsequentResponse}}

<br>

#### 8 Dispenser - Re-Release Prescription

The dispenser can now download the modified prescription for dispensing. This is similar to step 2.

