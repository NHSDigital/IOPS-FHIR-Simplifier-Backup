## {{page-title}}

In this example, the **Message Broker** system is akin to a **Shared Record** platform an also acts as an **events notification** system.

{{render:api-architecture-message-broker-events}}{:img-resonsive}

<br />

(1) The prescribing system creates the MedicationRequest with a valid externally referencable `identifer` and **POST**s this to the Message Broker. The `MedicationRequest` is triggered when the `MedicationRequest.status` = `active`. The message broker adds the logical `id` on receipt.

(2) The message broker triggers an event, to notify subscribing systems of the new `MedicationRequest`; the dispensing system must be a subscriber for this event.

(3) The dispensing system **GET**s the `MedicationRequest` from the shared record system using the `identifer`. 

(4) The dispensing system creates the `MedicationDispense` with a valid externally referencable `identifer` and **POST**s this to the shared record system. The `MedicationDispense` is triggered when the `MedicationDispense.status` = `completed`. The message broker adds the logical `id` on receipt. 

(5) The message broker triggers an **event notification** to notify subscribing systems of the new `MedicationDispense`; the prescribing system must be a subscriber for this event.

(6) The prescribing system **GET**s the `MedicationDispense` from the message broker using the `identifer`.

(7) On receipt, the prescribing system can set the `MedicationRequest.status` = `completed`. 

---
