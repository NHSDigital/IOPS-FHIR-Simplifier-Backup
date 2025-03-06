## {{page-title}}

Existing relationships for a person can be found by searching on the id of the RelatedPerson resource. There would have been a previous query (for example Search on Patient NHS Number) to identify RelatedPerson resources of interest (and to return their id).

```
GET https://pdsrepository.example.nhs.uk/FHIR/R4/RelatedPerson/{id}
```
or
```
GET https://pdsrepository.example.nhs.uk/FHIR/R4/RelatedPerson?_{id}
```
<br/>to return related Provenance resources
```
GET https://pdsrepository.example.nhs.uk/FHIR/R4/RelatedPerson?_{id}&_revinclude=Provenance:target

```
This request is then submitted to the Personal Demographics Service via [FHIR RESTful API](https://hl7.org/fhir/R4/http.html)  


### Search Examples

Without Provenance
```
GET https://pdsrepository.example.nhs.uk/FHIR/R4/RelatedPerson/RelatedPerson-NHS-9100000009
```
or
```
GET https://pdsrepository.example.nhs.uk/FHIR/R4/RelatedPerson?_id=RelatedPerson-NHS-9100000009
```
Example response:
- {{pagelink:Home/FHIR-Assets/Examples/Bundle-Searchset-Related-Person-patient-identifier-query.page.md}}

<br/><br/>
With Provenance
```
GET https://pdsrepository.example.nhs.uk/FHIR/R4/RelatedPerson?_id=RelatedPerson-NHS-9100000009&_revinclude=Provenance:target
```
Example response:
- {{pagelink:Home/FHIR-Assets/Examples/Bundle-Searchset-Related-Person-and-Provenance-patient-identifier-query.page.md}} 
