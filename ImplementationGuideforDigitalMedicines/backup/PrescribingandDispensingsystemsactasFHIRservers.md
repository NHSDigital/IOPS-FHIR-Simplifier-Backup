## {{page-title}}

The most simple architecture for interoperability between a single prescribing system and single dispensing system.

{{render: api-architecture-both-rx-and-disp-are-fhir-servers-simple}}{:img-resonsive}

<br />

(1) The prescribing system creates the `MedicationRequest` with a valid externally referencable `identifer` and **POST**s to the dipensing system which adds the logical `id` on receipt. The `MedicationRequest` is triggered when the `MedicationRequest.status` = `active`.

(2) The dispensing system creates the `MedicationDispense` with a valid externally referencable `identifer` and **POST**s to the prescribing system which adds the logical `id` on receipt. The `MedicationDispense` is triggered when the `MedicationDispense.status` = `completed`. 

(3) On receipt, the prescribing system can set the `MedicationRequest.status` = `completed`. 

---