## {{page-title}}

Should the patient choose to order to a one off nomination this can simply be done by including the ODS code of the one-off nominated pharmacy in the `input` element of the `Task` resource.

Example:
```json
        "input": [
            {
                "type": {
                    "coding": [
                        {
                            "system": "https://fhir.hl7.org.uk/GPConnect-PrescriptionOrderingParameters",
                            "code": "preferred-performer",
                            "display": "Preferred performer"
                        }
                    ]
                },
                "valueIdentifier": {
                    "system": "https://fhir.nhs.uk/Id/ods-organization-code",
                    "value": "FLM49"
                }
            }
        ]
 ```