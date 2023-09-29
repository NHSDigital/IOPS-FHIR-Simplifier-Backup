## {{page-title}}

| FHIR Exchange | API | FHIR Resource Profile |
|--
| FHIR RESTful  | [PUT /Task/(prescription-order-reference)](https://digital.nhs.uk/developer/api-catalogue/electronic-prescription-service-fhir#api-Dispensing-return) | {{pagelink:NHSDigital-Task-duplicate-2}} |

A prescription may be downloaded, but never dispensed by the pharmacy, for example if the pharmacy cannot supply the prescribed medication items. To allow the patient to visit a different dispenser the prescription must be returned to the EPS using the `PUT /Task` interaction . Once returned, the prescription should be removed from the local System.

Note. The `PUT /Task` interaction can be submitted when no user’s smartcard is present provided this is a system-triggered function rather than a user initiated one. An example would be when the system returns an invalid prescription without human intervention. 

If no response is received after 60 seconds, then assume failure. The System should automatically resubmit the ‘Dispense Proposal Return’ interaction. If it fails the second time then the user must be informed of a possible system failure and that the issue needs to be reported to the local service help desk.

### Example

For `acute` and `continuous` prescriptions this will be the `Short Form Prescription ID` (MedicationRequest.groupIdentifier)

`PUT /Task/83C40E-A23856-00123C`

Payload:

- {{pagelink:TaskReturnPrescriptionOrder-duplicate-2}} 

For `continuous-repeat-dispensing` prescriptions this is taken from the `Bundle.identifier.value` of the prescription-order which is to be returned.

`PUT /Task/0dd4773e-938f-4cc4-87bf-047e07657b27`

### Build Notes

- {{pagelink:PrescriptionCancellations-duplicate-2}}

