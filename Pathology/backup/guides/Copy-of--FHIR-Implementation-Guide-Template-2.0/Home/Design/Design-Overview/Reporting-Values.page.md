---
topic: DesignReportingValues
---
### Reporting Values
This section provides additional guidance on reporting values.

#### Reporting different types of test result
Individual test results are reported in the value[x] element of an Observation resource.

In FHIR, the value[x] construct allows a choice of datatype to be returned, appropriate to the datatype of the result. It is strongly recommended that implementers are familiar with the FHIR datatype documentation (linked below) to ensure correct representation of results.

| Value types           | FHIR datatype guidance    |
| --- | --- |
| valueQuantity         | [Quantity](https://hl7.org/fhir/r4/datatypes.html#Quantity)                   |
| valueCodeableConcept  | [CodeableConcept](https://hl7.org/fhir/r4/datatypes.html#CodeableConcept)     |
| valueString           | [string](https://hl7.org/fhir/r4/datatypes.html#string)                       |
| valueBoolean          | [boolean](https://hl7.org/fhir/r4/datatypes.html#boolean)                     |
| valueInteger          | [integer](https://hl7.org/fhir/r4/datatypes.html#integer)                     |
| valueRange            | [Range](https://hl7.org/fhir/r4/datatypes.html#Range)                         |
| valueRatio            | [Ratio](https://hl7.org/fhir/r4/datatypes.html#Ratio)                         |
| valueSampledData      | [SampledData](https://hl7.org/fhir/r4/datatypes.html#SampledData)             |
| valueTime             | [time](https://hl7.org/fhir/r4/datatypes.html#time)                           |
| valueDateTime         | [dateTime](https://hl7.org/fhir/r4/datatypes.html#dateTime)                   |
| valuePeriod           | [Period](https://hl7.org/fhir/r4/datatypes.html#Period)                       |

<br>

#### Reporting units
When reporting Quantities, systems SHOULD report relevant units for the quantity value.

* If a code for the unit is present, the system SHALL also be present
* UCUM is the preferred system for reporting units i.e. system = [http://unitsofmeasure.org](http://unitsofmeasure.org)

<br>

#### Reporting coded values using Read Codes ###
While coded SNOMED CT values are preferred, e.g.:

```xml
<code>
    <coding>
        <system value="http://snomed.info/sct"/>
        <code value="1000651000000109”/>
        <display value="Serum potassium level"/>
    </coding>
</code>
```

if a translation or mapping to SNOMED is not available, reporting coded values using Read codes is permitted, e.g.:

```xml
<code>
    <coding>
        <code value="44I4.00"/>
        <display value="Serum potassium"/>
        <system value="http://read.info/readv2"/>
    </coding>
</code>
```
<br>

#### Reporting qualified reference ranges ###

The PMIP EDIFACT messaging standard provides a mechanism to report a reference range for the test undertaken. A low and/or a high bound can be reported. Values with a low bound only are interpreted as greater than low bound. Values with a high bound only are interpreted as less than high bound.

---