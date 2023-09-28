## `identifier`

This should be populated with a globally unique and persistent identifier. This should be scoped by a provider specific namespace for the identifier.

Where consuming systems are integrating data from this resource to their local system, they should persist this identifier.

This will allow cross-referencing of a `MedicationDispense` within a prescribing system, and unique identification of a `MedicationDispense` within a shared record.

---
