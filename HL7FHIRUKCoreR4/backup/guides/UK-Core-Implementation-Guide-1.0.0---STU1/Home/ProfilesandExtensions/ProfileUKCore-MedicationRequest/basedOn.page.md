## `basedOn`

A reference to any number of `CarePlan`, `ImmunizationRecommendation`,`MedicationRequest` or `ServiceRequest` resources.

**Recommendation**: To reference a previous medication request use `priorPrescription` instead of this element.

If the clinical system has implemented the `CarePlan` resource, a logical link to the care plan for which the medication request is based has business benefit.

Any resource being referenced SHOULD conform to the following profiles/resources:

- <a href="https://hl7.org/fhir/R4/careplan.html">CarePlan Resource</a>
- <a href="https://www.hl7.org/fhir/r4/immunizationrecommendation.html">ImmunizationRecommendation Resource</a>
- {{pagelink:Profile-MedicationRequest-cd6802ba-6531-4cf0-b080-e1aee806f6f0}}
- <a href="https://hl7.org/fhir/R4/servicerequest.html">ServiceRequest Resource</a>

---
