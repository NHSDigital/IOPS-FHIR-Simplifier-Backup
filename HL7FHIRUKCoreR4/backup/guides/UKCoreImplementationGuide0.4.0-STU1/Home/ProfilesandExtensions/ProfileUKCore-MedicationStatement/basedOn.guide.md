## `basedOn`

This element should normally be used to link to a `MedicationRequest` which authorised the medication.

This element could potentially reference all medication requests relating to the medication or relevant instances of `CarePlan` or `ServiceRequest`.

This should not be confused with `MedicationStatement.derivedFrom` which should only be used to reference information that can’t be referenced here.

The resource being referencedused should conform to one of the following:

- {{pagelink:Profile-MedicationRequest-cd6802ba-6531-4cf0-b080-e1aee806f6f0}}
- <a href="https://simplifier.net/hl7fhirukcorer4/ukcorecareplan">UKCore-CarePlan Profile.</a>
- <a href="https://simplifier.net/hl7fhirukcorer4/ukcoreservicerequest">UKCore-ServiceRequest Profile.</a>
---
