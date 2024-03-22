## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle required" title="Required"></span> Required

<h5><ins>Guidance</ins></h5>

### Observations

This **MAY** be used for the component part of a blood pressure that is recorded as a triple or to carry qualifying data to the main observation code.

This **MAY** be used for inbound referrals.

### Blood Pressure

#### Systolic component

`component.code` - The clinical code that represents systolic part of the blood pressure.

`component.valueQuantity` - The value of the observation. This **MUST** be a ‘quantity’ data type and the units used **MUST** be ‘mm[Hg]’.

`component.dateAbsentReason` - If there is no code or value in this component, then a data absent reason may be populated.

`component.interpretation` - A human-readable clinical summary relating to a test result and/or additional notes provided by the laboratory - for example, the specimen has haemolysed or has leaked.

`component.referenceRange` - The reference range provides a guide for interpretation of the results.

Where a reference range contains a less than `<` or greater than `>` operator it should be written to the referenceRange.text element as these operators are not supported in this context.

#### Diastolic component

`component.code` - The clinical code that represents systolic part of the blood pressure.

`component.valueQuantity` - The value of the observation. This **MUST** be a ‘quantity’ data type and the units used **MUST** be ‘mm[Hg]’.

`component.dateAbsentReason` - If there is no code or value in this component, then a data absent reason may be populated.

`component.interpretation` - A human-readable clinical summary relating to a test result and/or additional notes provided by the laboratory - for example, the specimen has haemolysed or has leaked.

`component.referenceRange` - The reference range provides a guide for interpretation of the results.

Where a reference range contains a less than `<` or greater than `>` operator it should be written to the referenceRange.text element as these operators are not supported in this context.

<h5><ins>Example</ins></h5>

```xml
<component>
    <code>
        <coding>
            <system value="http://snomed.info/sct" />
            <code value="1091811000000102" />
            <display value="Diastolic arterial pressure (observable entity)" />
        </coding>
    </code>
    <referenceRange>
        <low>
            <code value="mm[Hg]" />
            <system value="http://unitsofmeasure.org" />
            <unit value="millimeter of mercury" />
            <value value="60" />
        </low>
        <high>
            <code value="mm[Hg]" />
            <system value="http://unitsofmeasure.org" />
            <unit value="millimeter of mercury" />
            <value value="80" />
        </high>
        <type>
            <coding>
                <code value="normal" />
                <system value="http://hl7.org/fhir/ValueSet/referencerange-meaning" />
                <display value="Normal Range" />
            </coding>
        </type>
    </referenceRange>
    <valueQuantity>
        <code value="mm[Hg]" />
        <system value="http://unitsofmeasure.org" />
        <unit value="millimeter of mercury" />
        <value value="92" />
    </valueQuantity>
    <interpretation>
        <system value="http://terminology.hl7.org/CodeSystem/v2-0078" />
        <code value="H" />
        <display value="High" />
    </interpretation>
</component>
```