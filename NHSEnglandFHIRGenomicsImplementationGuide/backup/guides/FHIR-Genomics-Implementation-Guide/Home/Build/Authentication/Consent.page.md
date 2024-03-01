## {{page-title}}

Consent within Genomics can be split into two main categories:
* General consent to having genetic/genomic testing performed, including consent obtained from family members for cascade testing
* Consent allowing for storage and secondary use of data, e.g. for research. Most relevant to WGS test requests, allowing storage of data in the National Genomic Research Library.

### Consent for Testing

Consent for testing is assumed to have been taken when submitting a test request to the Genomic Medicine Service. As of publication, capturing of this consent information is not considered in scope for storage in the central broker, however, this information can be represented using FHIR Consent resources. Guidance on how this information should be captured if general consent is later deemed in scope for the GMS.

Currently Consent for Testing is expected to be captured as part of the Unified Genomic Record, alongside wider consent, e.g. to have family members contacted regarding testing etc.

### Consent for Research

Currently, representation of Consent for Research within the Genomic Medicine Service is limited to the [Record of Discussion form](https://github.com/NHSDigital/NHSDigital-FHIR-Genomics-ImplementationGuide/blob/04ab4bc353a3c002613c422ecfc9aea6ab38c1c7/documents/nhs-genomic-medicine-service-record-of-discussion-form.pdf), [Young Person Assent Form](https://github.com/NHSDigital/NHSDigital-FHIR-Genomics-ImplementationGuide/blob/f74753a2d203ceb0703f1acbbf85675bc0638f18/documents/nhs-genomic-medicine-service-young-persons-assent-form.pdf) or [Consultee Declaration Form](https://github.com/NHSDigital/NHSDigital-FHIR-Genomics-ImplementationGuide/blob/f74753a2d203ceb0703f1acbbf85675bc0638f18/documents/nhs-genomic-medicine-service-genomic-consultee-declaration-1.pdf). Within GMS payloads these are modelled as a QuestionnaireResponses, based upon the relevant FHIR {{pagelink:Home/Examples/Questionnaire}} resources.

It is expected that this QuestionnaireResponse will be wrapped/referenced from a Consent resource to capture the status of the discussion and categorise the consent as consent for research.