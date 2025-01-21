## {{page-title}}

RelatedPerson's for a patient can be found by searching on the patient's NHS Number.

```
GET https://pdsrepository.example.nhs.uk/FHIR/R4/RelatedPerson?patient:identifier=https://fhir.nhs.uk/Id/nhs-number|{nhsNumber}
```

This request is then submitted to the Personal Demographics Service via [FHIR RESTful API](https://hl7.org/fhir/R4/http.html)  


### Search Example

```
GET https://pdsrepository.example.nhs.uk/FHIR/R4/RelatedPerson?patient:identifier=https://fhir.nhs.uk/Id/nhs-number|9000000017
```

Example response:

- {{pagelink:Home/FHIR-Assets/Examples/Bundle-Searchset-Related-Person-patient-identifier-query.page.md}}
