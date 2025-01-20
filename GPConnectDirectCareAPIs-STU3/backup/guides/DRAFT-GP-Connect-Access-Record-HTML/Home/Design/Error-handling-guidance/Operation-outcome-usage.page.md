## {{page-title}}

The FHIR standard allows for an `OperationOutcome` to be returned for any/all errors both for Operations and for RESTful CRUD API calls.

- operation APIs **MUST** return an `OperationOutcome` in the event of an error
- RESTful APIs **MUST** return an `OperationOutcome` when a specific error code has for a certain situation (i.e. no patient consent to share)
- RESTful APIs **MUST** return an `OperationOutcome` when any other unexpected error occurs containing debug details in the `Diagnostics` field