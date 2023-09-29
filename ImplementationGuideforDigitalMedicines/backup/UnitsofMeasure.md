## {{page-title}}

A unit of measure is required when [describing a dosage](ElementDosage) and can be supplied via one of two code systems:

### Preferred: Unified Code for Units of Measure (UCUM)

[The Unified Code for Units of Measure](http://unitsofmeasure.org) (UCUM) is preferred and should be used where possible.

Examples of when a UCUM unit of measure would be used are:

- gram (g)
- milliliter (ml)
- percent (%)

e.g.
```xml
<quantity>
    <value value="12.5" />
    <unit value="milliliter" />
    <system value="http://unitsofmeasure.org" />
    <code value="ml" />
</quantity>
```

### Alternative: SNOMED-CT

In the instance where a UCUM unit of measure is not defined, use a [SNOMED-CT](https://datadictionary.nhs.uk/data_elements/unit_of_measurement__snomed_ct_dm_d_.html) unit of measure instead. All units of measure are descendants of concept [`767524001 | Unit of measure (qualifier value)`](https://termbrowser.nhs.uk/?perspective=full&conceptId1=767524001&edition=uk-edition,999000691000001104) which includes both UCUM and non-UCUM codes.

Concept [`732935002 | Unit of presentation (unit of presentation)`](https://termbrowser.nhs.uk/?perspective=full&conceptId1=732935002&edition=uk-edition), which is also a descendant of the Unit of measure concept, holds a list non-UCUM units of measure that are used within prescribing:

Examples of where a SNOMED-CT unit of measure would typically be used are:

- tablet
- capsule
- ampoule
- patch

e.g.
```xml
<quantity>
    <value value="2" />
    <unit value="tablet" />
    <system value="http://snomed.info/sct" />
    <code value="428673006" />
</quantity>
```
---
