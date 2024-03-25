## {{page-title}}
In the case where the code was entered into the clinical system using a legacy coding system, the code will have been mapped to a SNOMED translation.

However, in SNOMED, all concept ids always have more than one associated description: all have at least one fully specified name and at least one additional associated synonym. Of these, exactly one fully specified name and one synonym will be declared to be “preferred” at any point in time within a Realm Language Reference Set, but which terms are designated “preferred” can and does change over time.

Therefore, in most cases where such mappings have been created, they will have been mapped to an explicit pairing of one SNOMED CT concept id and one of its legitimate description ids. The particular descriptionId selected may also correspond to the preferred term but often does not.

Exceptionally, mappings may correspond to a SNOMED CT concept id only and so no particular description is declared in the map. In these cases the description originally entered by the clinician in the legacy coding system is considered to be the clinically relevant text.

```xml
<code>
   <coding>
      <code value="44I4.00"/>
      <display value="Serum potassium"/>
      <system value="http://read.info/readv2"/>
      <userSelected value="true"/>
      <!--flags the coding originally actually selected by the user -->
   </coding>
   <coding>
      <extension url="https://fhir.hl7.org.uk/STU3/StructureDefinition/Extensioncoding-sctdescid">
         <extension url="descriptionId">
         <valueId value="2573011000000117"/>
         </extension>
      </extension>
      <system value="http://snomed.info/sct"/>
      <code value="1000651000000109”/>
      <display value="Serum potassium level"/>
   </coding>
   <text>Serum potassium</text>
 <!-- what the user saw on screen, from a data entry template -->
</code>
```

```json
{
  "code": {
    "coding": [
      {
        "extension": [
          {
            "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
            "extension": [
              {
                "url": "descriptionId",
                "valueId": "2573011000000117"
              }
            ]
          }
        ]
      },
      {
        "code": "44I4.00",
        "display": "Serum potassium",
        "system": "http://read.info/readv2",
        "userSelected": "true"
      }
    ]
  }
}
```

```xml
<code>
   <coding>
      <code value="B76..14"/> <!— term code = 14 ie not V2 Preferred term -->
      <display value="Mole of skin"/> <!— text for V2 term code = 14 -->
      <system value="http://read.info/readv2"/>
      <userSelected value="true"/> <!-- coding actually selected by user -->
   </coding>
   <coding>
      <code value="X78Uv"/> <!— no term code, so CTV3 PT is implied? -->
      <display value="Benign melanocytic naevus of skin"/> <!— text of V3 PT -->
      <system value="http://read.info/ctv3"/>
   </coding>
   <coding>
      <extension url="https://fhir.hl7.org.uk/STU3/StructureDefinition/Extensioncoding-sctdescid">
         <extension url="descriptionId">
         <valueId value="1787065011"/> <!— not the SNOMED PT -->
         </extension>
         <extension url="descriptionDisplay">
         <valueString value="Mole of skin"/> <!— text for id = 1787065011 -->
         </extension>
      </extension>
      <system value="http://snomed.info/sct"/>
      <code value="400010006”/> <!— SNOMED conceptId -->
      <display value="Melanocytic naevus of skin"/> <!— text of SNOMED PT -->
   </coding>
   <text>Moles</text> <!-- what user saw on screen, from data entry template -->
</code>
```

```json
{
  "code": {
    "coding": [
      {
        "code": "B76..14",
        "display": "Mole of skin",
        "system": "http://read.info/readv2",
        "userSelected": "true"
      },
      {
        "code": "X78Uv",
        "display": "Benign melanocytic naevus of skin",
        "system": "http://read.info/ctv3"
      },
      {
        "system": "http://snomed.info/sct",
        "code": "400010006",
        "display": " Melanocytic naevus of skin",
        "extension": [
          {
            "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
            "extension": [
              {
                "url": "descriptionId",
                "valueId": "1787065011"
              },
              {
                "url": "descriptionDisplay",
                "valueString": "Mole of skin"
              }
            ]
          }
        ]
      }
    ],
    "text": "Moles"
  }
}
```
