## {{page-title}} - Handling of 'No known allergies'

There can be an explicit assertion of ‘No Known Allergies’ using the SNOMED 'No known allergy' hierarchy [716186003 | No known allergy](https://termbrowser.nhs.uk/?perspective=full&conceptId1=716186003&edition=uk-edition), that contains six child concepts. The parent concept, or any child concept may be used.

XML
``` xml
<code>
  <coding>
    <system>http://snomed.info/sct</system>
    <code>409137002</code>
    <display>No known drug allergy (situation)</display>
  </coding>
</code>
```




JSON
``` json
{
"code": {
        "coding":  [
            {
                "system": "http://snomed.info/sct",
                "code": "409137002",
                "display": "No known drug allergy (situation)"
            }
        ]
    }
}
```

If other `AllergyIntolerance` resources exist in the patient record with a `clinicalStatus` of `active` then the system must ignore the 'No Known Allergies' resource instance. The existence of recorded and active allergies takes precedence over instances of 'No Known Allergies' records.

---