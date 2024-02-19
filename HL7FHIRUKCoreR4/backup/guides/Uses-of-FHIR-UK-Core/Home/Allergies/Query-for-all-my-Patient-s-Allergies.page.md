## {{page-title}}

## Business Use Case
As a clinical practitioner, I want to view all the current known allergies or intolerances for a patient, so that I can safely prescribe a medication.

## Search
#### Search using AllergyIntolerance.patient element for all allergies and intolerances
```
GET [base]/AllergyIntolerance?patient=[patient]
```
Example: <a style="font-family:'Courier New'" href="http://hapi.fhir.org/baseR4/AllergyIntolerance?patient=30163">http://hapi.fhir.org/baseR4/AllergyIntolerance?patient=30163</a>  

---

#### Search filtering on AllergyIntolerance.patient & AllergyIntolerance.code for any resources that are not inactive or resolved

<a style="font-family:'Courier New'" href="http://hapi.fhir.org/baseR4/AllergyIntolerance?_filter=patient%20eq%2030163%20and%20(clinical-status%20ne%20resolved%20and%20clinical-status%20ne%20inactive)">http://hapi.fhir.org/baseR4/AllergyIntolerance?_filter=patient%20eq%2030163%20and%20(clinical-status%20ne%20resolved%20and%20clinical-status%20ne%20inactive)</a>
 