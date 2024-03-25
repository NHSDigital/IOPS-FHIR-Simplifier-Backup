## {{page-title}}

In this case, the description id represents a term that is different from the preferred term and therefore the description will be different from that used to populate the code.coding.display element. In this case, the extension for descriptionDisplay shall be populated with the term corresponding to the descriptionId.

```xml
<code>
    <coding>
        <extension url="https://fhir.hl7.org.uk/STU3/StructureDefinition/Extensioncoding-sctdescid">
            <extension url="descriptionId">
            <valueId value="37443015"/>
            </extension>
            <extension url="descriptionDisplay">
            <valueString value="Heart attack"/>
            </extension>
        </extension>
        <code value="22298006"/>
        <display value="Myocardial infarction"/>
        <system value="http://snomed.info/sct"/>
        <userSelected value="true"/>
    </coding>
</code>
```

```json
{
    "code": {
        "coding": [{
            "extension": {
                "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
            "extension": [{
                "url": "descriptionId",
                "valueId": "37443015"
            },
            {
                "url": "descriptionDisplay",
                "valueString": "Heart attack"
            }
        ]
        },
        "code": "22298006",
        "display": "Myocardial infarction",
        "system": "http://snomed.info/sct",
        "userSelected": "true"
        }]
    }
}
```