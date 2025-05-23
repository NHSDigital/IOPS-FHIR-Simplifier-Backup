# {{page-title}}

To illustrate how the FHIR `Dosage` structure should be used for inpatient infusion use cases.

Infusions are complex because they may be dispensed and prepared in three ways;

1. Dispensed and prepared by the hospital pharmacy and delivered to the ward
2. Dispensed by the hospital pharmacy and prepared on the ward
3. Dispensed by the hospital pharmacy as a pre-prepared and dm+d coded product for the ward

This difference changes the use of the `MedicationDispense` resources. The initiating `MedicationRequest` and any resulting `MedicationAdministration` resource should not be different due to the above but we will verify this as part of creating these implementation guidance examples.

---
