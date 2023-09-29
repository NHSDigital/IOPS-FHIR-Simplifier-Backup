## Element: `priorPrescription` <span class="mro-circle optional" title="Optional"></span>

An optional element for when either the ePMA or pharmacy system would benefit from being able to link re-supply requests with a previous request.

The published FHIR specifications described this element is slightly different ways in different parts of the FHIR specification:

1. A link to a resource representing an earlier order related order or prescription.
2. An order or prescription that is being replaced.

The following guidance applies to each use case.

### Linking to an earlier request

A medication request that is a re-supply medication request based on a previous request referenced within `priorPrescription`. This would allow both the ePMA and pharmacy systems to logically link requests and add verification checks to flag any differences to the user.

### Linking to an order that is being replaced

The `medicationRequest` being replaced will be referenced within `priorPrescription`. It would be expected that the referenced resource would be updated with a status of `cancelled`, `entered-in-error` or `stopped`.

This will allow both the ePMA and pharmacy systems to make it clear to the human user that one medication request replaces another.

---