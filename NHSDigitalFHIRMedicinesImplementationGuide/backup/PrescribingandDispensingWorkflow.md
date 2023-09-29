## {{page-title}}

Prescribing and dispensing workflow consists of several transactions. 

| Transaction | Description |
|--
| {{pagelink:PrescriptionOrdering}} | The process of sending a prescription order requests to a pharmacy |
| {{pagelink:PrescriptionDownloadAndDispensing}} | The process of sending dispense notifications to EPS, these are responses to the prescription order requests |
| {{pagelink:PrescriptionClaiming}} | The process of claim for dispensed medications |
| {{pagelink:PrescriptionManagement}} | Interactions with EPS to manage the prescription workflows |

{{render:EPSWorkflow}} 

The three workflow messages use a FHIR interaction style called [FHIR Messaging](https://www.hl7.org/fhir/messaging.html) and the messages are sent to a generic endpoint called `$process-message`. This style of interaction is like HL7 v2 messages such as RDE_O01 and HL7 v3 messages used in the previous version of EPS. Details on the relationships with the previous version of EPS can be found here {{pagelink:HL7v3andFHIRInteractions-duplicate-2.md }}

A more detailed description of the workflow is described below:

{{render:EPSSequenceDiagram}}

<br> 

- The `prescription-order` needs to be signed. This process for signing is described in the [Digital signatures section of the EPS API](https://digital.nhs.uk/developer/api-catalogue/electronic-prescription-service-fhir#api-Prescribing-preparePrescription) 
- The Prescribing System sends the `prescription-order` message EPS which will then deliver the prescription to the Dispensing System.
- The Pharmacist issues the medication and sends a `dispense-notification` message to EPS. Multiple `dispense-notification` messages may be sent to support the recording of partial dispensing (when the full quantity of requested medication is not available for dispensing in one event).
- Once dispensing events against the prescription have been completed, the dispensing system will then issue a reimbursement `claim` message to EPS.
- EPS will forward the `claim` to NHS BSA along with the original signed `prescription-order`.
