## {{page-title}}

### View the initial Proxy Access Request

Is referenced in the `focus` element of the receieved Proxy Access Request Verification FHIR Task. 


```json
 "focus": {
        "type": "QuestionnaireResponse",
        "reference": "https://proxyservice.example.nhs.uk/FHIR/R4/QuestionnaireResponse-QuestionnaireResponse-proxy-access-request"
    },
```

#### Message Semantics

```
GET {baseUrl}/QuestionnaireReponse/{id}
```

##### Example 

```
GET https://proxyservice.example.nhs.uk/FHIR/R4/QuestionnaireResponse-QuestionnaireResponse-proxy-access-request
```

### View the proposed Consent

Is referenced in the `input` array of the receieved Proxy Access Request Verification FHIR Task. 

```json
 {
            "type": {
                "coding":  [
                    {
                        "system": "https://fhir.nhs.uk/England/NationalProxy",
                        "code": "Consent"
                    }
                ]
            },
            "valueReference": {
                "reference": "https://proxyservice.example.nhs.uk/FHIR/R4/Consent/Consent-Consent-national-proxy-proposed",
                "type": "Consent"
            }
        }
```

#### Message Semantics

This is also [IHE Privacy Consent on FHIR (PCF) - Access Consent [ITI-108]](https://profiles.ihe.net/ITI/PCF/ITI-108.html)

```
GET {baseUrl}/Consent/{id}
```

##### Example 

```
GET https://proxyservice.example.nhs.uk/FHIR/R4/Consent/Consent-Consent-national-proxy-proposed
```

### View the proposed RelatedPerson

Is referenced in the `input` array of the receieved Proxy Access Request Verification FHIR Task. 

```json
 {
            "type": {
                "coding":  [
                    {
                        "system": "https://fhir.nhs.uk/England/NationalProxy",
                        "code": "Proxy"
                    }
                ]
            },
            "valueReference": {
                "reference": "https://nhsdigital.github.io/nhsengland-spine-specification-sandbox/RelatedPerson-RelatedPerson-NHS-9100000009",
                "type": "RelatedPerson"
            }
        }
```

#### Message Semantics

```
GET {baseUrl}/RelatedPerson/{id}
```

##### Example 

```
GET https://proxyservice.example.nhs.uk/FHIR/R4/RelatedPerson/RelatedPerson-RelatedPerson-NHS-910000000
```
