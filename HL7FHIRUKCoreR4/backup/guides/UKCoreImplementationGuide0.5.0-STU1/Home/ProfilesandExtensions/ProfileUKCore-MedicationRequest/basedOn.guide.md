## `basedOn`

Optional.

A reference to any number of `CarePlan`, `MedicationRequest`, `ServiceRequest` or `ImmunizationRecommendation` resources.

**Recommendation**: To reference a previous medication request use `priorPrescription` instead of this element.

If the clinical system has implemented the `CarePlan` resource, a logical link to the care plan for which the medication request is based has business benefit.

Any resource being referenced should conform to the following profiles/resources:

- <a href="https://simplifier.net/hl7fhirukcorer4/ukcorecareplan">UKCore-CarePlan Profile.</a>
- {{pagelink:Profile-MedicationRequest-cd6802ba-6531-4cf0-b080-e1aee806f6f0}}
- {{pagelink:Profile-ServiceRequest-6b7f601e-1517-4596-8a8e-0f8f40caa095}}
- <a href="https://www.hl7.org/fhir/r4/immunizationrecommendation.html">UKCore-ImmunizationRecommendation Profile.</a>


---
