## `basedOn`

Any resource being referenced SHALL conform to the following profiles/resources:

- [Profile UKCore-CarePlan](https://simplifier.net/hl7fhirukcorer4/ukcorecareplan)
- {{pagelink:Profile-MedicationRequest}}
- {{pagelink:Profile-ServiceRequest}}
- [ImmunizationRecommendation Resource](https://www.hl7.org/fhir/r4/immunizationrecommendation.html)

**Recommendation**: To reference a previous medication request use `MedicationRequest.priorPrescription` instead of this element.

If the clinical system has implemented the `CarePlan` resource, a logical link to the care plan for which the medication request is based has business benefit.



---
