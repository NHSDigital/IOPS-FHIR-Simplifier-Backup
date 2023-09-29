# {{page-title}}

This implementation guide covers a number of use cases, for which there may be various technical implementations using different types of interaction. Whilst the data shared within an interaction will be the same, e.g. the sharing of a `MedicationRequest` or `MedicationStatement`, the nature of the interaction may vary. Within one implementation a record may be shared via a RESTful **GET** operation. Within another, sharing the same FHIR resource(s) may be via a RESTful **POST** operation.

Depending on the chosen interoperability architecture, the use of specific FHIR data elements will change.

### Use of `identifier`

The `identifier` is the most important element of a FHIR resource for interoperability. It acts as the **externally facing unique business identifier** for the resource. A key phrase from the FHIR R4 standard is;
> [for `identifier`] ...All resources that have an identifier element support searching by the identifier, so that records can be located by that method.

### Use of `id`

By contrast, the resource `id` is normally an internally facing unique logical identifier. Within the FHIR R4 standard is the key phrase related to the logical `id` where it is:
> [for `id`] ...assigned by the server responsible for storing it

Where a nationally understood unique identifier exists for a resource then it could be feasible to use this as both the `identifer` and `id`. An example would be the unique code for an NHS organisation, where the **ODS Code** is an established national standard.

### Use of `status`

The different types of business `status` for `MedicationRequest` and `MedicationDispense` resources made visible within systems may change depending the interoperability architecture. 

Within some architectures, only valid end-states may be exposed, e.g. `'active'` MedicationRequests. This would be the case when resources are `POST`ed to a FHIR server. The sharing of resources with a status such as `'draft'` or `'entered-in-error'` via a `POST` operation is illogical.

Within other architectures, when systems query the system acting as the FHIR server, records of any state may be returned. This may include resources with a status such as `'draft'` or `'entered-in-error'`.

---