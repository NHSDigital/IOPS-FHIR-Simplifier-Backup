## {{page-title}}

## Business Use Case
*As a pharmacist, I want know if my patient has an Ibuprofen allergy, so I can dispense the correct medications.*
<br><br>

## Search
#### Search using `AllergyIntolerance.patient` and `AllergyIntolerance.code`.
```
GET [base]/AllergyIntolerance?patient=30163&code=387207008
```
Example: <a style="font-family:'Courier New'" href="http://hapi.fhir.org/baseR4/AllergyIntolerance?patient=30163&code=387207008">http://hapi.fhir.org/baseR4/AllergyIntolerance?patient=30163&code=387207008</a>  
<br><br>
#### Search using `AllergyIntolerance.patient` and `AllergyIntolerance.code` where the `code.system` is SNOMED CT.
```
GET [base]/AllergyIntolerance?patient=30163&code=http%3A%2F%2Fsnomed.info%2Fsct|387207008
```
Example: <a style="font-family:'Courier New'" href="http://hapi.fhir.org/baseR4/AllergyIntolerance?patient=30163&code=http%3A%2F%2Fsnomed.info%2Fsct|387207008">http://hapi.fhir.org/baseR4/AllergyIntolerance?patient=30163&code=http%3A%2F%2Fsnomed.info%2Fsct|387207008</a>  
<br><br>
#### Search using `AllergyIntolerance.patient` and `AllergyIntolerance.code` where the `code.value` contains `ibuprofen`.
```
GET [base]/AllergyIntolerance?patient=30163&code:text=ibuprofen
```
 
Example: <a style="font-family:'Courier New'" href="http://hapi.fhir.org/baseR4/AllergyIntolerance?patient=30163&code:text=ibuprofen">http://hapi.fhir.org/baseR4/AllergyIntolerance?patient=30163&code:text=ibuprofen</a>  

---