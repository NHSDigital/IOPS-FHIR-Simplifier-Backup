## {{page-title}}

This API will only allow orders for repeat prescriptions. Acute prescriptions should be handled via other methods until this functionality is supported.

A patient can add supporting evidence or additional information to a request which ensures that the practitioner will have all relevant information upon reviewing a medication order. For example, a patient can include additional details such as where they are going on holiday or if they are reaching the end of their previous prescription.

The details of the request are bundled together into MedicationRequest:
- Status (requested, approved, rejected)
- Intent (order)
- Medication (name of medication)
- Authored On (DD/MM/YY)
- Note (free text supporting information provided by the user)
- Status Reason (to be used when request is rejected)
- Requester (patient)
- Dosage Instructions
- Previous Prescription (ID linking to the previous prescription issued)
- Prescription Type (repeat)

As part of the ordering process, the patient can check the pharmacy that the prescription will be sent to (once approved by a practitioner) for electronic prescriptions. This is where they can choose to send their prescription to an alternative pharmacy as a **one-off nomination**. This functionality is only available for electronic prescriptions which are processed via EPS. 

When a patient chooses a one-off nomination the MedicationRequest bundle will also include location details, which can then be sent on for EPS to process should the practitioner approve the request:
- ODS Site Code
- Name
- Type
- Hours of Operation

For paper prescriptions the patient will be informed to collect their prescription from their practitioner.