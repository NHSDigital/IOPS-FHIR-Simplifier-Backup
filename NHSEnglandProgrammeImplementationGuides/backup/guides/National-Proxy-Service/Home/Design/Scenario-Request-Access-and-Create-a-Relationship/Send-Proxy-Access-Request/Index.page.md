## {{page-title}}

The **Proxy Application** creates a FHIR QuestionnaireResponse which matches the FHIR Questionnaire definition {{pagelink:Home/FHIR-Assets/Questionnaire/Proxy-Access-Request.page.md}}.

This request is then submitted to the national proxy service via [FHIR RESTful API](https://hl7.org/fhir/R4/http.html)  


 ```
POST https://proxyservice.example.nhs.uk/FHIR/R4/QuestionnaireReponse
```
### Event Payload Example

{{pagelink:Home/FHIR-Assets/Examples/QuestionnaireResponse-Proxy-Access-Request.page.md}}

