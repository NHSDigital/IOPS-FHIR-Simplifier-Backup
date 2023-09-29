## {{page-title}}

| Actor | Description |
| ----- | ----------- |
|Patient Facing Service (PFS) | This actor is the consumer application which is used to manage medication and prescriptions on behalf of the patient. This system places the prescription order and sends the cancellation of the prescription. |
| Practitioner System | This actor is the application which is used to process prescriptions and medication on behalf of the practitioner. The system will send prescriptions on to the Electronic Prescription Service (EPS) once approved by a practitioner for dispensing. |
| Prescription Management API | This actor is the communication touch point between the PFS and Practitioner System allowing transactions to take place. There is no human actor behind this system. |
| Practitioner | This human actor is a person who is directly or indirectly involved in the provisioning of healthcare to the patient. This actor may be a clinician or clinical support staff. |
| Patient | This human actor is the subject of medication treatments. They make use of PFS to manage their medication and prescription orders. |
