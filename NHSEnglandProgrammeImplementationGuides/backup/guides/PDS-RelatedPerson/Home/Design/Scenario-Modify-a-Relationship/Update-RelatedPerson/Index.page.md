## {{page-title}}

An existing RelatedPerson can be updated by the following:

```
PUT https://pdsrepository.example.nhs.uk/FHIR/R4/RelatedPerson/{id}
```

Where `id` is the current id of the resource. This request is then submitted to the Personal Demographics Service via [FHIR RESTful API](https://hl7.org/fhir/R4/http.html)  


### Update Example

```
PUT https://pdsrepository.example.nhs.uk/FHIR/R4/RelatedPerson/PDS-RelatedPerson-D1EDA4B8-Example
```

See {{pagelink:Home/FHIR-Assets/Examples/RelatedPerson-D1EDA4B8-Example.page.md}} for existing resource.