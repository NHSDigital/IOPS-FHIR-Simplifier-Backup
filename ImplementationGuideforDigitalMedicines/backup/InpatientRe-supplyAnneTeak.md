# {{page-title}}

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
  This example is based on an implementation using <code>FHIR Messages</code> where the provider/sender system is using an HTTP <code>POST</code> to the consumer/receiver system acting as a FHIR Server.
</div>

## Patient Journey: Anne Teak

1. Anne is admitted as an inpatient and is prescribed **Amoxicillin 500mg** orally three times daily for a suspected chest infection. A re-supply of this medication is requested on the ward. The Trust ePMA system sends a FHIR Message containing a `MedicationRequest` to the Trust pharmacy system  [[Example 1](#example1)].
2. Pharmacy dispenses this medication. The Trust pharmacy system notifies the ePMA system as a FHIR Message containing a `MedicationDispense` [[Example 2](#example2)].

---
