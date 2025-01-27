## {{page-title}}

The National Proxy Registry is updated based on the values present in the `out` array in the response of the FHIR Task {{pagelink:Home/FHIR-Assets/Examples/Task-Consent-Verification-Completed.page.md}}.

```json
"output":  [
        {
            "type": {
                "coding":  [
                    {
                        "system": "https://fhir.nhs.uk/England/NationalProxy",
                        "code": "decision"
                    }
                ]
            },
            "valueCodeableConcept": {
                "coding":  [
                    {
                        "system": "https://fhir.nhs.uk/England/NationalProxyConsentStatus",
                        "code": "proxy-approved"
                    }
                ]
            }
        }
    ]
```

An example Consent relating to a `proxy-approved` can be found in {{pagelink:Home/FHIR-Assets/Examples/Consent-confirmed.page.md}}
A Consent updated for `proxy-rejected` can be found in {{pagelink:Home/FHIR-Assets/Examples/Consent-rejected.page.md}}
