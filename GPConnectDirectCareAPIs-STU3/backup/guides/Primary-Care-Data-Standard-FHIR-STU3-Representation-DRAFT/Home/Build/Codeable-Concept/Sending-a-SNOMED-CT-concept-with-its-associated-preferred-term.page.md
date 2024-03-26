## {{page-title}}
When sending a SNOMED CT concept id with its preferred term then
code.coding.extension.descrpitionId, code.coding.code and code.coding.system SHALL be
populated.

In the example below, the descriptionId is populated with the descriptionId for the preferred
term but there is no descriptionDisplay as the concept id was entered by the user and the
preferred term was displayed to them when it was added.

```xml
<code>
    <coding>
        <extension url="https://fhir.hl7.org.uk/STU3/StructureDefinition/Extensioncoding-sctdescid">
            <extension url="descriptionId">
            <valueId value="37436014"/>
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
            "extension": [{
            "url":     "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
            "extension": [{
                "url": "descriptionId",
                "valueId": "37436014"
                }]
            }],
            "code": "22298006",
            "display": "Myocardial infarction",
            "system": "http://snomed.info/sct",
            "userSelected": "true"
        }]
    }
}
```