## `identifier`

The `identifier` is the most important element of a FHIR resource for interoperability. It acts as the **externally facing unique business identifier** for the resource. A key phrase from the FHIR R4 standard is;
> [for `identifier`] ...All resources that have an identifier element support searching by the identifier, so that records can be located by that method.

### Provider Systems

It is recommended that the `identifier` value is a Universally Unique Identifier (UUID) as there is no nationally recognised business indentier for an instance of a recorded allergy or intolerence.

### Consumer Systems

Consumer systems **MUST** consume this data.

---