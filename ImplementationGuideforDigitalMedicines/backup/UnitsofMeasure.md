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

Examples of where a SNOMED-CT unit of measure would typically be used include:

- tablet
- capsule
- ampoule
- patch

At this time, there is some overlap within SNOMED-CT for non-UCUM codes within descendants of [`732935002 | Unit of presentation (unit of presentation)`](https://termbrowser.nhs.uk/?perspective=full&conceptId1=732935002&edition=uk-edition) and [`408103002 | Unit of drug administration (unit of presentation)`](https://termbrowser.nhs.uk/?perspective=full&conceptId1=408103002&edition=uk-edition). 

Both these hierarchies include units such as `tablet` therefore as a provider/sender system, either code can be used, and as a consumer/receiver system, either code can be received and accepted.

For example

```xml
<quantity>
    <value value="2" />
    <unit value="tablet" />
    <system value="http://snomed.info/sct" />
    <code value="428673006" /> <!-- from "Unit of drug administration" --> 
</quantity>
```
Or

```xml
<quantity>
    <value value="2" />
    <unit value="tablet" />
    <system value="http://snomed.info/sct" />
    <code value="732936001" /> <!-- from "Unit of presentation" -->
</quantity>
```

---
