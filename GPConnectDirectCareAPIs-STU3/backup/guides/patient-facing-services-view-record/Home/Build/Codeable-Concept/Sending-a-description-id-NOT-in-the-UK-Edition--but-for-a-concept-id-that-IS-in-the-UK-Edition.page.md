## {{page-title}}

Includes the case where the description id is locally declared to be the preferred term

```xml
<code>
    <coding>
        <extension url="https://fhir.hl7.org.uk/STU3/StructureDefinition/Extensioncoding-sctdescid">
            <extension url="descriptionId”>
            <valueId value="787121000006116"/>
            <!-- descriptionId from EMIS namespace -->
            </extension>
            <extension url="descriptionDisplay">
                <valueString value="Ideal weight"/>
            </extension>
        </extension>
        <code value="170804003"/>
        <!-- conceptId from SNOMED International CORE -->
        <display value="Ideal body weight"/>
        <system value="http://snomed.info/sct"/>
        <userSelected value="true"/>
    </coding>
</code>
```

```json
{
  "code": {
    "coding": {
      "extension": [
        {
          "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
          "extension": [
            {
              "url": "descriptionId",
              "valueId": "787121000006116"
            },
            {
              "url": "descriptionDisplay",
              "valueString": "Ideal weight"
            }
          ]
        }
      ],
      "code": "170804003",
      "display": "Ideal body weight",
      "system": "http://snomed.info/sct",
      "userSelected": "true"
    }
  }
}
```