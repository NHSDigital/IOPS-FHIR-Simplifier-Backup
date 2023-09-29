## Timing Elements: `duration`, `bounds` and `count`

Adding constraints, bounds or limits to a dosage instruction.


### Sub-elements: `duration` and `durationMax`

A dosage instruction to be administered over a period of time is defined by a `duration` and / or a `durationMax`. These relate to the duration of a single administration so would be applicable for an infusion or potentially a transdermal patch. 

The FHIR specification states that if there is a `durationMax`, there must be a `duration`.

The use of duration does not apply to medicines that are swallowed or otherwise instantly administered.

**over 8 hours**

```xml
<timing>
	<repeat>
		<duration value="8"/>
		<durationUnit value="h" />
	</repeat>
</timing>
```

**over 10 to 15  minutes**

```xml
<timing>
	<repeat>
		<duration value="10"/>
		<durationMax value="15"/>
		<durationUnit value="min"/>
	</repeat>
</timing>
```

### Sub-element: `boundsDuration`

An instruction to limit a single course of medication uses the `bounds` structure. This can be implemented in three ways;

- `boundsDuration` - a period of time, for example: _for 7 days_
- `boundsRange` - a low / high quantity, for example: _for 2 to 3 weeks_
- `boundsPeriod` - a date / time start to end period, for example: _from 22/02/2021 to 04/03/2021_

**for 7 days**

```xml
<timing>
	<repeat>
		<boundsDuration>
			<value value="7"/>
			<unit value="day"/> 
			<system value="http://unitsofmeasure.org"/>
			<code value="d"/>
		</boundsDuration>

	</repeat>
</timing>
```

**for 2 to 3 weeks**

```xml
<timing> 
	<repeat>
		<boundsRange>
			<low>
				<value value="2"/>
				<unit value="week"/> 
				<system value="http://unitsofmeasure.org"/>
				<code value="wk"/>
			</low>
			<high>
				<value value="3"/>
				<unit value="week"/>
				<system value="http://unitsofmeasure.org"/>
				<code value="wk"/>
			</high>
		</boundsRange>
	</repeat>
</timing>
```

**from 22/02/2021 to 04/03/2021**

```xml
<timing>  
	<repeat>
        <boundsPeriod>
            <start value="2021-02-22"/>
            <end value="2021-03-04"/>
        </boundsPeriod>
	</repeat>	
</timing>
```

### Sub-elements: `count` and `countMax`

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>Note:</strong>
    Use <b>count</b> and <b>countMax</b> with caution as there are other elements within the Dosage structure that will often be more appropriate.
</div>

An instruction for a set number of doses, including the use case of “once”, plus also any maximum number of doses, is defined by `count` and `countMax`. 

Whilst the `count` is within `repeat` it does not mean repeat a number of additional times. 

- A `count` of 1 means adminster a dose once. 
- A `count` of 3 means administer 3 doses.

The FHIR specification states if there is a `countMax`, there must be a `count`.

**take once**

```xml
<timing>
	<repeat>
		<count value="1"/>
	</repeat>
</timing>
```

**take twice**

```xml
<timing>
	<repeat>
		<count value="2"/>
	</repeat>
</timing>
```

**take three times**

Clincal Example: **Teicoplanin** - 10 mg/kg - every 12 hours - **for 3 doses**, then 6 to 10 mg/kg - daily

```xml
<timing>
	<repeat>
		<count value="3"/>
	</repeat>
</timing>
```

**take three to five times**

```xml
<timing>
	<repeat>
		<count value="3"/>
		<countMax value="5"/>
	</repeat>
</timing>
```

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>Alternatives:</strong>
    Examples where alternatives to using <b>count</b> within a Dosage instruction would be more appropriate.
</div>

**take once**

Instead of using `<count value="1"/>` use `<frequency value="1"/>`.

**an oral solid - 2 tablets - twice a day - take 14 times**

Using a `<count value="14"/>` is confusing. Is this "*take 2 tablets twice a day for 14 days*" or "*take 2 tablets twice a day and take 14 tablets in total, hence for 7 days*"? It would be better to express as a **duration**.

```xml
<duration value="7"/>
<durationUnit value="d" />
```

---