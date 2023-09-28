## `code` (Mandatory)

Identifies the causative agent for the allergy or intolerance.

When recording an allergy to a medication substance, the provider system should use a dm+d concept class.

- **National Health Service dictionary of medicines and devices combination drug Virtual Therapeutic Moiety (VTM)** – just the drugs, no formulation. May be additional concepts to those in SNOMED-CT (SCT) hierarchy.
- **National Health Service dictionary of medicines and devices Virtual Medicinal Product (VMP)** - generic drug products and also generic appliance/ device concepts. May be additional concepts to those in SCT hierarchy and will support the recording of allergies to bandages and dressings etc. Device/appliances are concepts that would not be within scope of SCT pharmaceutical/biologic product hierarchy.
- **National Health Service dictionary of medicines and devices Actual Medicinal Product (AMP)** – branded drug products and branded appliance/device concepts that would not be within scope of SCT pharmaceutical/ biologic product hierarchy.
- **National Health Service dictionary of medicines and devices ingredient** – just the drug ingredients, no formulation. May be additional concepts to those in SCT hierarchy. Important to have this in addition to VTM as some things may be more specific at VTM level for example things only available as combinations where VTM would only be the combination also VTM may not identify the salt but this concept class would support that.

Alternatively, or when the allergy is not recorded against a medication substance, the relevant set of SNOMED CT codes is a union of the following.

- Substance hierarchy [105590001 | substance](https://termbrowser.nhs.uk/?perspective=full&conceptId1=105590001&edition=uk-edition) 

- Product hierarchy [373873005 | Pharmaceutical/biologic product(product)](https://termbrowser.nhs.uk/?perspective=full&conceptId1=373873005&edition=uk-edition) 

- No known allergy hierarchy [716186003 | No known allergy](https://termbrowser.nhs.uk/?perspective=full&conceptId1=716186003&edition=uk-edition). To record a positive affirmation of no known allergies.

- [196461000000101 | transfer-degraded drug allergy (record artifact)](https://termbrowser.nhs.uk/?perspective=full&conceptId1=196461000000101&edition=uk-edition)

- [196471000000108 | transfer-degraded non-drug allergy (record artifact)](https://termbrowser.nhs.uk/?perspective=full&conceptId1=196471000000108&edition=uk-edition).

### Using transfer degraded drug / non-drug allergy codes

Degraded drug allergy codes can be used in three scenarios, with examples.

1. If only a text representation of the allergy is known.


XML
``` xml

<code>
  <coding>
    <system value="http://snomed.info/sct"/>
    <code value="196471000000108"/>
    <display value="transfer-degraded non-drug allergy(record artifact)"/>
  </coding>
  <text value="Latex"/>
</code>
```

JSON
``` json

"code": {
        "coding":  [
            {
                "system": "http://snomed.info/sct",
                "code": "196471000000108",
                "display": "transfer-degraded non-drug allergy(record artifact)"
            }
        ],
        "text": "Latex"
    }
```

2. If a text representation of the allergy is known but any associated coding is not recognised by the system.

XML
``` xml
<code>
  <coding>
    <system value="http://snomed.info/sct"/>
    <code value="196461000000101"/>
    <display value="transfer-degraded drug allergy (record artifact)"/>
  </coding>
  <text value="9339101000001105 | Septrin"/>
</code>

```

JSON
``` json
"code": {
        "coding":  [
            {
                "system": "http://snomed.info/sct",
                "code": "196461000000101",
                "display": "transfer-degraded drug allergy (record artifact)"
            }
        ],
        "text": "9339101000001105 | Septrin"
    }
```

**Note:** “Septrin” is a long discontinued brand name of an antibiotic.

3. If a pre-coordinated allergy code is known which this is not part of the permitted value set for causative agent defined above.


XML
``` xml
<code>
  <coding>
    <system value="http://snomed.info/sct"/>
    <code value="196461000000101"/>
    <display value="transfer-degraded drug allergy (record artifact)"/>
  </coding>
  <text value="213020009 | Allergy to egg protein"/>
</code>
```
JSON
``` json
"code": {
        "coding":  [
            {
                "system": "http://snomed.info/sct",
                "code": "196461000000101",
                "display": "transfer-degraded drug allergy (record artifact)"
            }
        ],
        "text": "213020009 | Allergy to egg protein"
    }
```

### Use of plain text only 

The representation of the causative agent as text is supported within the FHIR standard but this should only be used as a last resort if a suitable coded term does not exist within the SNOMED-CT terminology or if using a degraded allergy code is not appropriate.

### Use of `nullFlavor`

The UK Core recommendation is that the `nullFlavor` is **not used** for the causative agent, even though it is permitted within the FHIR standard.

### Provider Systems

Provider systems **MUST** provide this data. 

### Consumer Systems

Consumer systems **MUST** consume this data.

---
