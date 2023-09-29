## {{page-title}}

{{render: api-architecture-disp-is-fhir-server-simple}}{:img-resonsive}

<br />

(1) The prescribing system creates the `MedicationRequest` with a valid externally referencable `identifer` and **POST**s to the dipensing system which adds the logical `id` on receipt. The `MedicationRequest` is triggered when the `MedicationRequest.status` = `active`.

(2) The prescribing system queries the dispending system via a **GET** using the unique `identifer` from the `MedicationRequest`, i.e. "get the dispensing record for this request". The dispensing system assigns the logical `id`. The GET request may be sent at any time so the dispensing system may choose to expose `MedicationDispense.status` values that represent both in-progress and end-states for the dispensing record.

(3) When the dispensing system returns a `MedicationDispense.status` of `completed`, the prescribing system can set the `MedicationRequest.status` = `completed`. 

---