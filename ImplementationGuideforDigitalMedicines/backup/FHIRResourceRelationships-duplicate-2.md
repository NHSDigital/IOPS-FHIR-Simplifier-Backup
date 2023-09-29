## FHIR Resource Relationships

This implementation guidance defines a Minimum Viable Product (MVP) for each FHIR Resource required to support the target use case of medication dispense from a hospital ePMA system to a hospital pharmacy system.

An implementation is recommended to adhere to the MVP but can also choose to implement other elements from the chosen FHIR standard. For the purposes of this guidance, an “implementation” is the partnership between an ePMA system supplier and a hospital pharmacy system supplier within a given Trust.

The MVP requires the implementation of four FHIR Resources:

- [MedicationDispense](#)
- [Medication](Medication)
- [Patient](Patient)
- [Performer(Practitioner)](Practitioner)

<br />

{{render: medication-dispense }}{: .img-responsive }

The `MedicationDispense` can reference many other FHIR resources but the four above are required for the recommended MVP.

---