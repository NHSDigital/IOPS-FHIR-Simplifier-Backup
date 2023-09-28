## `performer`
Indicates who performed the immunization event.

XML
```xml
<performer>
    <actor>
        <type value="Practitioner"/>
            <identifier>
                <system value="https://fhir.hl7.org.uk/Id/nmc-number"/>
                <value value="5566789"/>
                <display value="HOLDING, Rafferty"/>
            </identifer>
    </actor>            
    <actor>
        <type value="Organization"/>
            <identifier>
                <system value="https://fhir.nhs.uk/Id/ods-organization-code"/>
                <value value="C4B2A"/>
                <display value="ELLAND ROAD STADIUM - COVID VACCINATION CENTRE"/>
            </identifer>
    </actor>
</performer>

```

JSON
```json
{
"performer":  [
        {
            "actor": {
                "type": "Practitioner",
                "identifier": {
                    "system": "https://fhir.hl7.org.uk/Id/nmc-number",
                    "value": "5566789"
                },
                "display": "HOLDING, Rafferty"
            }
        },
        {
            "actor": {
                "type": "Organization",
                "identifier": {
                    "system": "https://fhir.nhs.uk/Id/ods-organization-code",
                    "value": "C4B2A"
                },
                "display": "ELLAND ROAD STADIUM - COVID VACCINATION CENTRE"
            }
        }
    ],
}
```
---