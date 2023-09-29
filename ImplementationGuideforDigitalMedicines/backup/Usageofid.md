## {{page-title}}

By contrast, the resource `id` is normally an internally facing unique logical identifier. Within the FHIR R4 standard is the key phrase related to the logical `id` where it is:
> [for `id`] ...assigned by the server responsible for storing it

Where a nationally understood unique identifier exists for a resource then it could be feasible to use this as both the `identifer` and `id`. An example would be the unique code for an NHS organisation, where the **ODS Code** is an established national standard.

---