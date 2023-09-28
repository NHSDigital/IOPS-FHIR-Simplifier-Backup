## `clinicalStatus`

A value from a required terminology binding containing the values;
- `active`
- `inactive`
- `resolved`.

The FHIR standard states this element **SHALL** be present if `verificationStatus` is **not** `entered-in-error`, but **SHALL NOT** be present if `verificationStatus` is `entered-in-error`.

### Provider Systems

Provider systems **MUST** provide this data. 

### Consumer Systems

Consumer systems **MUST** consume this data.

### Handling changes in clinical status

A recorded allergy may be subsequently proven to have a different clinical status, e.g. from `active` to `inactive`. In this scenario provider systems should **create a new instance** of this resource to reflect the change of clinical status.

This is opposed to updating the existing instance of the resource. This resource has no data element that could convey a *last updated* date. Also the action of updating the resource may not be picked up by consumer systems. Creating a new instance of the resource is the safer implementation approach.

---
