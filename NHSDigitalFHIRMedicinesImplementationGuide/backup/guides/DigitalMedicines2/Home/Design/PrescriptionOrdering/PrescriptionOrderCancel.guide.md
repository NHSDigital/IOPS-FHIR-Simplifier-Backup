## {{page-title}}

| FHIR Exchange | API |Event Type | FHIR (Bundle) Message Definition |
|--
| FHIR Messaging | [POST /$process-message](https://digital.nhs.uk/developer/api-catalogue/electronic-prescription-service-fhir#api-Prescribing-send-prescription-order-update-message) | `prescription-order-update` | {{pagelink:prescription-order-update-duplicate-2}} |

<br>

Electronic prescriptions can be cancelled by any prescriber (or staff) who has the correct authorisation on their smartcard. This can be done at any point until the prescription is dispensed and given to the patient.

The `prescription-order-update` message is similar to the `prescription-order` message and the main differences are the `CommunicationRequest` and `Provence` resources are not required.

Only one MedicationRequest can be cancelled, it is not possible to cancel the entire `prescription-order`. To cancel the entire `prescription-order`, multiple `prescription-order-update` messages must be used, one for each `MedicationRequest` in the `prescription-order`.

The same `MedicationRequest` resource used within the `prescription-order` message can be reused with the following amendments:

| Source Data Item| FHIR Element | Additional Conformance |
|--
| | meta.lastUpdated	 | Date of cancellation |
| | status	| <b>MUST</b> be `cancelled` |
| | statusReason.coding.code | <b>MUST</b> be present and use a code from {{pagelink:DM-MedicationRequest-Status-Reason-duplicate-2}} |
| | statusReason.text  | <b>SHOULD</b> be present. If not present `statusReason.coding.display` will be used.  | 
| Cancellation requestor | extension (ResponsiblePractitioner) [NHSDigital-PractitionerRole](https://simplifier.net/guide/NHSDigital/NHSDigital-PractitionerRole) | Person and their organization requesting cancellation of the prescription item. This is **MUST** be present if the requestor is not the same as the author. GMC Reference Number **MUST NOT** be used as a Practitioner identifier |


{{render:process-update-message}}

When a prescription has already been downloaded by the patient's nominated pharmacy it cannot be cancelled and EPS will send a cancellation rejected message back to the prescriber. 

The prescriber should then contact the dispenser to return the whole prescription to the NHS Spine. If this is possible (the medication has not been dispensed), the dispenser returns the prescription to EPS and then EPS sends a subsequent cancellation to the prescriber. 

{{render:process-update-message-multi}}

### Build Notes

- {{pagelink:PrescriptionCancellations-duplicate-2}}

##### Prescription Order Response

The response to a `prescription-order-update` is a `prescription-order-response` FHIR Message and is defined in {{pagelink:prescription-order-response-duplicate-2}}