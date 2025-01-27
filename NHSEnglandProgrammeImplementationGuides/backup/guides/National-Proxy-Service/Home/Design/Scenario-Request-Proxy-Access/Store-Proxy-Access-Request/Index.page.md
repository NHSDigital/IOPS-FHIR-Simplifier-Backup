## {{page-title}}

The proxy access request is stored on the National Proxy Registry. The process followed is HL7 Structured Data Capture [Form Data Extraction](https://build.fhir.org/ig/HL7/sdc/extraction.html) which takes the FHIR QuestionnaireResponse and creates:

- Consent
- RelatedPerson

on the National Proxy Registry

<plantuml>
@startuml


component service as "NHS England Proxy Service"
component FormDataExtraction as "[[https://build.fhir.org/ig/HL7/sdc/extraction.html Form Data Extraction]]"
component repository as "National Proxy Registry"

service -d-> FormDataExtraction: Proxy Access Request\n(FHIR QuestionnaireResponse)
service -d-> repository: Proxy Access Request\n(FHIR QuestionnaireResponse)
FormDataExtraction -d-> repository: FHIR RelatedPerson\nFHIR Consent


@enduml

</plantuml>

### Examples

- {{pagelink:Home/FHIR-Assets/Examples/QuestionnaireResponse-Proxy-Access-Request.page.md}}
- {{pagelink:Home/FHIR-Assets/Examples/Consent-proposed.page.md}}
- {{pagelink:Home/FHIR-Assets/Examples/Related-Person-91000000009.page.md}}
