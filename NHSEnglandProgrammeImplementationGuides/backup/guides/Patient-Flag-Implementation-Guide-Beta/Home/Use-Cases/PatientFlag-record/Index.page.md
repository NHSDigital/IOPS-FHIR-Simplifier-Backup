## {{page-title}}

This page shows the functional use cases provided by the PatientFlag API:

- Retrieve a set of top-level Flags (just the Flags with no associated resources)
- Retrieve a specific type of Flag with associated resources
- Add a top-level Flag
- Add a top-level Flag (and associated Additional Detail resources)
- Add/remove associated resources (with the dependency that a top-level flag must already be added/removed)
- Remove a top-level Flag (which will remove all associated resources)

This API is abstract only. Concrete specialisations of the API have been implemented to support Reasonable Adjustments and Female Genital Mutilation Flags.