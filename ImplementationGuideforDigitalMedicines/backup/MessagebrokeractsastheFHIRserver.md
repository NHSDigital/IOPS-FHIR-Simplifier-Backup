## {{page-title}}

In this example, the **Message Broker** system is akin to a **Shared Record** platform.

{{render:api-architecture-message-broker}}{:img-resonsive}

<br />

(1) The prescribing system creates the MedicationRequest with a valid externally referencable `identifer` and **POST**s this to the Message Broker. The `MedicationRequest` is triggered when the `MedicationRequest.status` = `active`. The message broker adds the logical `id` on receipt.

(2) The prescribing system directly sends an **event notification** to the dispensing system with the `identifer` for the `MedicationRequest`.

(3) The dispensing system **GET**s the `MedicationRequest` from the shared record system using the `identifer`. 

(4) The dispensing system creates the `MedicationDispense` with a valid externally referencable `identifer` and **POST**s this to the shared record system. The `MedicationDispense` is triggered when the `MedicationDispense.status` = `completed`. The message broker adds the logical `id` on receipt. 

(5) The dispensing system directly sends an **event notification** to the prescibing system with the `identifer` for the `MedicationDispense`.

(6) The prescribing system **GET**s the `MedicationDispense` from the message broker using the `identifer`.

(7) On receipt, the prescribing system can set the `MedicationRequest.status` = `completed`. 

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>Note</strong>: This architecture is close to that implemented by the  <a href='https://digital.nhs.uk/services/electronic-prescription-service'>Electronic Prescription Service</a> (EPS). The <strong>(2) event notification</strong> is implemented via a paper or electronic <i>token</i> containing the barcoded <code>identifier</code> (aka the EPS 'Prescription ID') that the patient presents to the pharmacy. Not yet implemented within the EPS are flows (5), (6) and (7).
</div>

---