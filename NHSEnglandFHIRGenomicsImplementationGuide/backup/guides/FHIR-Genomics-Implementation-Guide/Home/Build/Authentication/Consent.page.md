## {{page-title}}

Consent within Genomics can be split into two main categories:
* General consent to having genetic/genomic testing performed, including consent obtained from family members for cascade testing
* Consent allowing for storage and secondary use of data, e.g. for research. Most relevant to WGS test requests, allowing storage of data in the National Genomic Research Library.

### Consent for Testing

Consent for testing is assumed to have been taken when submitting a test request to the Genomic Medicine Service. As of publication, capturing of this consent information is not considered in scope for storage in the central broker, however, this information can be represented using FHIR Consent resources. Guidance on how this information should be captured if general consent is later deemed in scope for the GMS.

### Consent for Research

Currently, representation of Consent for Research within the Genomic Medicine Service is limited to the [Record of Discussion form](https://github.com/NHSDigital/NHSDigital-FHIR-Genomics-ImplementationGuide/blob/04ab4bc353a3c002613c422ecfc9aea6ab38c1c7/documents/nhs-genomic-medicine-service-record-of-discussion-form.pdf). Within GMS payloads this is modelled as a QuestionnaireResponse, based upon the {{pagelink:Questionnaire-Genomic-Testing}} FHIR Questionnaire resource.

It is expected that this QuestionnaireResponse will be wrapped/referenced from a Consent resource to capture the status of the discussion and categorise the consent as consent for research.