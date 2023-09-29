## {{page-title}}

The different types of business `status` for `MedicationRequest` and `MedicationDispense` resources made visible within systems may change depending the interoperability architecture. 

Within some architectures, only valid end-states may be exposed, e.g. `'active'` MedicationRequests. This would be the case when resources are `POST`ed to a FHIR server. The sharing of resources with a status such as `'draft'` or `'entered-in-error'` via a `POST` operation is illogical.

Within other architectures, when systems query the system acting as the FHIR server, records of any state may be returned. This may include resources with a status such as `'draft'` or `'entered-in-error'`.

---