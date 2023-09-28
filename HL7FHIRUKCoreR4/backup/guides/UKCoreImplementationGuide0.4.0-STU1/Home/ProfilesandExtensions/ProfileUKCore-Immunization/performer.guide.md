## `performer`
Indicates who performed the immunization event by reference. The resource being referenced should conform to one of the following: 

- {{pagelink:Profile-Organization-3826477b-c49f-45cd-a6a4-a179826dd3a8}}
- {{pagelink:Profile-Practitioner-96448d2b-cd33-42cb-b1db-f48ae31db401}}
- {{pagelink:Profile-PractitionerRole-91e0c0ae-8b79-41de-b8e1-4eeb30ab2565}}


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