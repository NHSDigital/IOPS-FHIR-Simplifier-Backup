## {{page-title}}

Standards for FHIR Documents are:

- NHS England
  - [Transfer of Care](https://digital.nhs.uk/services/interoperability-toolkit/developer-resources/transfer-of-care-specification-versions) FHIR STU3
  - [Digital Medicine](https://digital.nhs.uk/developer/api-catalogue/digital-medicine-fhir) FHIR STU3 depreceated
- HL7 International
  - [HL7 International Patient Summary Implementation Guide](https://build.fhir.org/ig/HL7/fhir-ips/)
- HL7 EU  
  - [HL7 Europe Laboratory Report](https://build.fhir.org/ig/hl7-eu/laboratory/branches/master/index.html)


Most documents use a mix of formats such as:

- pdf
- html
- png
- img

Health and Care has an additional format called [Clinical Document Architecture](https://en.wikipedia.org/wiki/Clinical_Document_Architecture). This comes in two HL7 versions

- [HL7 v3 CDA](https://www.hl7.org.uk/standards/hl7-standards/cda-clinical-document-architecture/)
- FHIR Documents - see below

These document formats are content standards and can be used with any of the interaction standards listed in the previous sections (i.e. IHE XDS, HL7 FHIR and V2). 

### FHIR Documents

[FHIR Documents](https://hl7.org/fhir/R4/documents.html) is a FHIR exchange standard for:

- exchanging resources
- exchanging a html representation of those resources and clinical narrative.

Example rendered FHIR Document:
{{render:diagrams-TechnicalFramework-SharedClinicalDocuments-FHIRDocumentRendered}}

This allows the recipient to either process the structured content and/or the html representation of the content.

The diagram below shows a generic content and is based on the [HL7 International Patient Summary Implementation Guide](https://build.fhir.org/ig/HL7/fhir-ips/)

{{render:diagrams-Interactions-FHIR-Document}}

FHIR Documents also cater for different levels of supplier/provider maturity as it can be both:

- A method of exchanging structured data
- A method of exchanging html documents.

So a receiving system which can't process the structured data would use the html representation. Another system may process the structured data.
A sending system would always include the html content and structured data which they support.



The use of both HL7 FHIR Documents and HL7 v3 CDA represent only a proportion of the documents used in health care. 

