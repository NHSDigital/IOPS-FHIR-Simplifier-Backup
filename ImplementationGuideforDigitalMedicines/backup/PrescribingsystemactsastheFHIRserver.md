## {{page-title}}

{{render: api-architecture-rx-is-fhir-server-simple}}{:img-resonsive}

<br />

(1) The prescribing system sends an **event notification** to the pharmacy system when a new `MedicationRequest` is ready for processing. The notification must include the external externally referencable `identifer`. The prescirbing system assigns the logical `id`.

(2) The prescribing system **GET**s the MedicationRequest using the `identifer`. The GET request may be sent at any time so the pharmacy system may choose to expose `MedicationRequest.status` values that represent both in-progress and end-states for the prescribing record.

(3) The dispensing system creates the `MedicationDispense` with a valid externally referencable `identifer` and **POST**s to the prescribing system which adds the logical `id` on receipt. The `MedicationDispense` is triggered when the `MedicationDispense.status` = `completed`.

(4) On receipt, the prescribing system can set the `MedicationRequest.status` = `completed`.  

---