## Element: `{{page-title}}`

The `dose[x]` and `rate[x]` elements within the Dosage structure have been combined in the FHIR R4 standard within `doseAndRate`. The underlying purpose and use is the same as per FHIR STU3 specification.

A dose or rate of medication can be described via one of the following methods. In both instances when considering Units of Measure note that UCUM is preferred.

### Sub-element: `Dosage.doseAndRate.doseQuantity`

The amount of medication per dose, as a [simple coded quantity](http://hl7.org/fhir/datatypes.html#SimpleQuantity).

```xml
<!-- Example A: 1 capsule -->
<doseAndRate>
    <doseQuantity>
        <value value="1"/>
        <unit value="capsule"/>
        <system value="http://snomed.info/sct"/>
        <code value="732937005"/>
    </doseQuantity>
</doseAndRate>

<!-- Example B: 30 milligrams -->
<doseAndRate>
    <doseQuantity>
        <value value="30"/>
        <unit value="milligram"/>
        <system value="http://unitsofmeasure.org"/>
        <code value="mg"/>
    </doseQuantity>
</doseAndRate>
```

For some dosing instructions, for example with **Methotrexate** dosing, it may be good clinical practice to express the dose using different units of measure, using two instances of the `doseAndRate` element. 

```xml
<!-- Example: for Methotrexate 2.5mg tablets -->
<text value="2 tablet (5 milligram)" />
<doseAndRate>
    <doseQuantity>
        <value value="2"/>
        <unit value="tablet"/>
        <system value="http://snomed.info/sct"/>
        <code value="428673006"/>
    </doseQuantity>
</doseAndRate>
<doseAndRate>
    <doseQuantity>
        <value value="5"/>
        <unit value="milligram"/>
        <system value="http://unitsofmeasure.org"/>
        <code value="mg"/>
    </doseQuantity>
</doseAndRate>
```

Within the `text` element, include the second quantity in brackets after the first dose quantity. The first dose quantity should be that which aligns with the unit dose form of the medication, i.e. Methotrexate tablets, so express as `"2 tablet (5 milligram)"` and not `"5 milligram (2 tablet)"`.

### Sub-element: `Dosage.doseAndRate.doseRange`

A dose that may be in a given low / high range.

```xml
<!-- for a dose between 7.5 to 30 milligram -->
<doseAndRate>
    <doseRange>
        <low>
            <value value="7.5"/>
            <unit value="milligram"/>
            <code value="mg"/>
            <system value="http://unitsofmeasure.org"/>
        </low>
        <high>
            <value value="30"/>
            <unit value="milligram"/>
            <code value="mg"/>
            <system value="http://unitsofmeasure.org"/>
        </high>
    </doseRange>
</doseAndRate>
```

A rate-based quantity, such as _30 ml per hour_, can be expressed as a `rateRatio` with coded numerator and denominator values.

Where the unit of measure for the ratio is defined within UCUM (see [Common UCUM Units](https://www.hl7.org/fhir/valueset-UCUM-common.xml)), for example, “milliliter per hour”, it can also be expressed using the simpler `rateQuantity` structure.

If the `doseRange.low` is omitted it should be interpreted as as dose "up to" the upper limit.

```xml
<!-- for a dose up to 30 milligram -->
<doseAndRate>
    <doseRange>
        <high>
            <value value="30"/>
            <unit value="milligram"/>
            <code value="mg"/>
            <system value="http://unitsofmeasure.org"/>
        </high>
    </doseRange>
</doseAndRate>
```

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>Recommendation</strong>: The FHIR standard allows the <code>doseRange.high</code> to be omitted but it is recommended not to support this. The absence of an upper limit for a dose range would be clinical bad practice.
</div>


### Sub-element: `Dosage.doseAndRate.rateRatio`

Where the rate is expressed as coded numerator and denominator values.

**at a rate of 30ml/hour using rateRatio**

```xml
<doseAndRate>
	<rateRatio>
		<numerator>
			<value value="30"/>
			<unit value="millilitre"/>
			<system value="http://unitsofmeasure.org"/>
			<code value="mL"/>
		</numerator>
		<denominator>
			<value value="1"/>
			<unit value="hour"/>
			<system value="http://unitsofmeasure.org"/>
			<code value="h"/>
		</denominator>
	</rateRatio>
</doseAndRate>
```

### Sub-element: `Dosage.doseAndRate.rateQuantity`
Where the unit of measure applicable to a rate is defined within UCUM which is mathematically equivalent to defining the rate using the more complex `rateRatio` structure.

**at a rate of 30ml/hour using rateQuantity**

```xml
<rateQuantity>
	<value value="30"/>
	<unit value="milliliters per hour"/>
	<system value="http://unitsofmeasure.org"/>
	<code value="mL/h"/>
</rateQuantity>
```

**at a rate of 1mcg/kg/hour using rateQuantity**

```xml
<doseAndRate>
	<rateQuantity>
		<value value="1"/>
		<unit value="microgram per kilogram per hour"/>
		<system value="http://unitsofmeasure.org"/>
		<code value="ug/kg/h"/>
	</rateQuantity>
</doseAndRate>
```

### Sub-element: `Dosage.doseAndRate.rateRange`

Where the unit of measure applicable to a rate range is defined within UCUM the `rateRange` structure can be used.

**give at 1-2 litres per minute using rateRange**
```xml
<doseAndRate>
    <rateRange>
		<low>
			<value value="1"/>
			<unit value="liter per minute"/>
			<system value="http://unitsofmeasure.org"/>
			<code value="L/min"/>
		</low>
		<high>
			<value value="2"/>
			<unit value="liter per minute"/>
			<system value="http://unitsofmeasure.org"/>
			<code value="L/min"/>
		</high>
	</rateRange>
</doseAndRate>
```

### Period of no (zero) administration

Where a dosage instruction includes a defined period of no (zero) administration then the `doseAndRate` element can be specified with a 0 (zero) quantity.

```xml
<rateQuantity>
    <value value="0" />
    <unit value="millilitre per hour" />
    <system value="http://unitsofmeasure.org" />
    <code value="mL/h" />
</rateQuantity>
```
or
```xml
<rateQuantity>
    <value value="0" />
    <unit value="capsule"/>
    <system value="http://snomed.info/sct"/>
    <code value="732937005"/>
</rateQuantity>
```


<!--See the complete example for [Colchicine tablets](DosageExamples-Wherefree-textinstructionsarerequired#Colchicinetablets) which includes an instruction for a period of time where medication should not be taken;

> Do not repeat course for 3 days

Another clinical example would be for a Lidocaine medicated plaster. A typical written dosage instruction would be;

> Apply 2 patches once daily to the affected area for up to 12 hours, followed by a 12-hour plaster-free period; to be applied to intact, dry, non-hairy, non-irritated skin.

The R4 Dosage structure cannot describe, in a machine readable way, the clauses "*Do not repeat course for 3 days*" and “*followed by a 12-hour plaster-free period*”.
-->

---