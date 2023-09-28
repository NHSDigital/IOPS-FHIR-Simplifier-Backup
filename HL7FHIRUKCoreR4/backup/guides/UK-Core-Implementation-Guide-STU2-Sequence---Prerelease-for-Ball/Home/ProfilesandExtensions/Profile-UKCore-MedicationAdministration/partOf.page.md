## `partOf`

An optional reference to a `Procedure` that could be used for medications given intraoperatively (during an operation / procedure) where there may not be a `MedicationRequest` resource to reference. A reverse reference could be added as ‘partOf’ of the Procedure resource. 

This element can also reference another `MedicationAdministration` resource. Where several medication administrations relate to the same MedicationRequest, the reference to the MedicationRequest within ‘request’ is sufficient for logical data linkage purposes. It may give additional business benefit to also logically link the MedicationAdministration resources using ‘partOf’. 

The resource being referenced SHALL conform to the one of the following:
- {{pagelink:Profile-MedicationAdministration-56616}}
- {{pagelink:Profile-Procedure-10775}}

---
