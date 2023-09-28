## `{{page-title}}`

This should be populated with a globally unique and persistent identifier. This should be scoped by a provider specific namespace for the identifier.

Where consuming systems are integrating data from this resource to their local system, they should persist this identifier.

This will allow cross-referencing of a `MedicationRequest` within a dispensing system, and unique identification of a `MedicationRequest` within a shared record.

---