# {{page-title}}

All electronic transfers of medication and allergy/intolerance information between NHS systems in England must use the Information Standards Notice [DAPB4013: Medicines and Allergy/Intolerance Data Transfer](https://digital.nhs.uk/data-and-information/information-standards/information-standards-and-data-collections-including-extractions/publications-and-notifications/standards-and-collections/dapb4013-medicine-and-allergy-intolerance-data-transfer). The deadline for complying with the Standard is March 2023.

To support compliance with the Standard, the self-service [FHIR Support Test Tool](Self-AssuranceGuidance#HowtoaccesstheFHIRsupporttesttool) is available from NHS Digital to assist system suppliers and NHS organisations in the technical development of their solutions. This supports development of `MedicationRequest`, `MedicationDispense` and `MedicationStatement` FHIR Resources.

The test tool is intended to complement existing development processes and will not replace or act as the source of validation for interoperability. Suppliers and providers should work together to implement safe solutions with governance / assurance appropriate to the specific delivery.  
In addition, to the support for the development of FHIR resources, the test tool supports validation for business rules for messages sent between ePMA and hospital pharmacy stock control systems.

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>Note</strong>: We recommend suppliers use the test tool early in the development process to avoid having to re-work messages at a later stage if they are found to be non-compliant.
</div>

## How to access the FHIR supporting guidance materials

For additional information on the scope and purpose of the FHIR test tool as well as guidance on completing your clinical risk and safety assessment, please email [medicinestandards@nhs.net](mailto:medicinestandards@nhs.net){: .nhsd-a-link } and a guide will be sent to you

---