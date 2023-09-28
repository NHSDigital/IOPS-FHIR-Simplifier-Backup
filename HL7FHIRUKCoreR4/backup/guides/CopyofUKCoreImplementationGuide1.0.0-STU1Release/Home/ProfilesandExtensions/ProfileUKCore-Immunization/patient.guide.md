## `patient`

The patient who either received or did not receive the immunization.

Only traced NHS/CHI/HSCNI Numbers **SHOULD** be used.

JSON

```json
{
"patient": {
                    "reference": "urn:uuid:edea022a-2d81-11eb-adc1-0242ac120002",
                    "type": "Patient",
                    "identifier": {
                        "system": "https://fhir.nhs.uk/Id/nhs-number",
                        "value": "9912003888"
                    }
                },
}
```

### Provider Systems

Provider systems **MUST** provide a `reference` and/or `identifier` **MUST** be provided that allows the consumer system to query another API if they need to access the complete **UKCore-Patient** resource. 

### Consumer Systems

Consumer systems **MUST** consume this data.

---