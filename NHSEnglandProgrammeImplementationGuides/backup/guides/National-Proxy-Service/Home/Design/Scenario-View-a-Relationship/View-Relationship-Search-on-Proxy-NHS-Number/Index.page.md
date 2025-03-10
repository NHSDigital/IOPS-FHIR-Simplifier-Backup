## {{page-title}}

Existing proxy relationships for a proxy can be found by searching on the proxy's NHS Number.

```
GET https://proxyrepository.example.nhs.uk/FHIR/R4/RelatedPerson?identifier=https://fhir.nhs.uk/Id/nhs-number|{nhsNumber}
```

This request is then submitted to the national proxy service via [FHIR RESTful API](https://hl7.org/fhir/R4/http.html)  


### Search Example

```
GET https://proxyrepository.example.nhs.uk/FHIR/R4/RelatedPerson?identifier=https://fhir.nhs.uk/Id/nhs-number|91000000009
```



Example response:

{{pagelink:Home/FHIR-Assets/Examples/Bundle-Searchset-Related-Person-identifier-query.page.md}}