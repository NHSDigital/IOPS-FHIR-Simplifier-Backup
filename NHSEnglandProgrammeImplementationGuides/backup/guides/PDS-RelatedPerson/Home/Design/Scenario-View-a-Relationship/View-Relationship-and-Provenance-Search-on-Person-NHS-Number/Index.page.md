## {{page-title}}

Existing RelatedPerson for a person can be found by searching on the person's NHS Number.

```
GET https://pdsrepository.example.nhs.uk/FHIR/R4/RelatedPerson?identifier=https://fhir.nhs.uk/Id/nhs-number|{nhsNumber}&_revinclude=Provenance:target
```

This request is then submitted to the Personal Demographics Service via [FHIR RESTful API](https://hl7.org/fhir/R4/http.html)  


### Search Example

```
GET https://pdsrepository.example.nhs.uk/FHIR/R4/RelatedPerson?identifier=https://fhir.nhs.uk/Id/nhs-number|91000000009&_revinclude=Provenance:target
```

Example response:
- {{pagelink:Home/FHIR-Assets/Examples/Bundle-Searchset-Related-Person-and-Provenance-identifier-query.page.md}} 
