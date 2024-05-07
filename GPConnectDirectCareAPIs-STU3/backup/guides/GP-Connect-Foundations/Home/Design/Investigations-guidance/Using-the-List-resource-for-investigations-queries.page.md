## {{page-title}}

The results of a query for investigations **MUST** return a `List` containing references to all the `DiagnosticReport` resources to represent each investigation report that is returned. The list code **MUST** be set to `887191000000108` for Investigations and results.

The `List` **MUST** be populated in line with the guidance on `List` resources.

If the `List` is empty, then an empty `List` **MUST** be returned with an `emptyReason` with the value `no-content-recorded`.