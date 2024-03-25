## {{page-title}}

```xml
<code>
    <coding>
        <extension url="https://fhir.hl7.org.uk/STU3/StructureDefinition/Extensioncoding-sctdescid">
            <extension url="descriptionId">
            <valueId value="253790221000087110"/>
            <!— from Canadian extension -->
            </extension>
            <extension url="descriptionDisplay”>
            <valueString value="Use of illicit drugs unknown"/>
            <!-- synonym from Canadian extension -->
            </extension>
        </extension>
        <code value="186782131000087106"/>
        <!-- conceptId from Canadian extension -->
        <display value="Use of illicit type drug unknown"/>
        <!-- preferred term from Canadian extension -->
        <system value="http://snomed.info/sct"/>
        <userSelected value="true"/>
    </coding>
    <text> Not known whether uses illicit drugs</text>
    <!-- what the user saw on screen, from a data entry template -->
</code>
```

```json
{
  "code": {
    "coding": {
      "extension": {
        "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
        "extension": [
          {
            "url": "descriptionId",
            "valueId": "253790221000087110"
          },
          {
            "url": "descriptionDisplay",
            "valueString": "Use of illicit drugs unknown"
          }
        ]
      },
      "code": "186782131000087106",
      "display": "Use of illicit type drug unknown",
      "system": "http://snomed.info/sct",
      "userSelected": "true"
    },
    "text": " Not known whether uses illicit drugs"
  }
}
```