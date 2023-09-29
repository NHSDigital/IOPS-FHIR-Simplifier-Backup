## {{page-title}}

For provider systems that support fully structured dosage instructions a complete Dosage structure **SHOULD** be populated as per implementation guidance.

- Where fully structured dosage instructions are not supported by provider systems `Dosage.text` and `Dosage.patientInstruction` **MUST** be populated as described below.
- All other elements that are part of the dosage datatype are optional, and **MAY** be populated in line with [ISN DAPB4013](https://digital.nhs.uk/data-and-information/information-standards/information-standards-and-data-collections-including-extractions/publications-and-notifications/standards-and-collections/dapb4013-medicine-and-allergy-intolerance-data-transfer).

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
    As such, the free-text representation of the dosage instruction <b>MUST BE PROVIDED</b> by sending systems, along with the structured dosage to ensure that receiving systems are able to interpret the dosage instruction.
</div>

A [separate guide covering structured dosage](https://simplifier.net/guide/ukcoreimplementationguideformedicines/Home?version=current) in great detail has been created by NHS England. The guidance is scoped for FHIR R4 `dosage` element; however, other than a slight change in element names, it still applies for FHIR STU3.




---