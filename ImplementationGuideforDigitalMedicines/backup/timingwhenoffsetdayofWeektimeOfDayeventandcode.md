## Timing Elements: `when`, `offset`, `dayOfWeek`, `timeOfDay`, `event` and `code`

A dosage instruction can be tied to the specific days, dates and times, plus life events related to eating or sleeping.

### Sub-elements: `when` and `offset`

The [when](http://hl7.org/fhir/stu3/datatypes-definitions.html#Timing.repeat.when) element ties to the regular life events of sleeping and eating, for example:

- `C` = event occurs at a meal
- `CM` = event occurs at breakfast
- `CD` = event occurs at lunch
- `CV` = event occurs at dinner
- `ACM` = event occurs `[offset]` before breakfast
- `PCM` = event occurs `[offset]` after breakfast

An `[offset]` allows the event to be tied to defined minutes before or after the event. The offset is an unsigned integer value so different codes within the when value-set are used to define if before or after, opposed to using a negative integer for timing before the event.

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">    <strong>Note 1:</strong> To ensure consistency across UK implementations, it is recommended that lunch is interpreted at the middle meal of a typical 3 meals a day routine, and dinner interpreted at the last meal of a typical 3 meals a day routine.
</div>

**Event occurs at breakfast**

```xml
<timing>
    <repeat>
        <when value="CM"/>
    </repeat>
</timing>
```

**Event occurs at 1 hour before breakfast**

```xml
<timing>
    <repeat>
        <when value="ACM"/>
        <offset value="60" />
    </repeat>
</timing>
```

**Event occurs at 1 hour after breakfast**

```xml
<timing>
    <repeat>
        <when value="PCM"/>
        <offset value="60" />
    </repeat>
</timing>
```

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">    <strong>Note 2:</strong> We recommend a maximum of one <code>when</code> event per medication administration. The FHIR standard allows for multiple <code>when</code> events but this could become confusing for a single administration.
</div>

For example:

<div class="nhsd-a-box nhsd-a-box--bg-red nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong class="emphasis-box__heading">Bad potentially confusing example:</strong>
    <br />
    daily - at breakfast, in the morning
</div>

```xml
<!-- "daily - at breakfast, in the morning" -->
<timing>
    <repeat>
        <frequency value="1"/>
        <period value="1"/>
        <periodUnit value="d"/>
        <when value="CM"/>
        <when value="MORN"/>
    </repeat>
</timing>
```

The above could be confused as two administrations. One at breakfast and another in the morning. Not everybody eats breakfast in the morning. What about those working night shifts?

Whereas when there are multiple administrations, multiple `when` events are less confusing.

```xml
<!-- "twice a day - in the morning, in the evening" -->
<timing>
    <repeat>
        <frequency value="2"/>
        <period value="1"/>
        <periodUnit value="d"/>
        <when value="MORN"/>
        <when value="EVE"/>
    </repeat>
</timing>
```

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">    <strong>Note 3:</strong> Where the meal related <code>when</code> codes of "C", "AC" or "PC" are used it is recommended to also include timing frequency instructions. This will ensure the medication is taken for the correct number of times in the day, e.g. "3 times a day, at a meal" or "twice a day, at a meal".
</div>

**Event occurs at a meal, further clarified with '3 times a day'**

```xml
<!-- 3 times a day - at a meal -->
<timing>
    <repeat>
        <frequency value="3"/>
        <period value="1"/>
        <periodUnit value="d"/>
        <when value="C"/>
    </repeat>
</timing>
```
<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">    <strong>Note 4:</strong> The FHIR <code>when</code> codes events relating to meals are for when the dosing instruction is related to timing. Where the primary intent of the dosing instruction is for the medication to be taken with food then include a SNOMED coded <code>additionalInstruction</code>.
</div>

**Event occurs with food**

```xml
<!-- with food -->
<additionalInstruction>
    <coding> 
        <system value="http://snomed.info/sct"/> 
        <code value="1116481000001105"/> 
        <display value="With food"/> 
    </coding>
</additionalInstruction>
```

**Event occurs in the morning, with food**

```xml
<!-- in the morning - with food -->
<timing>
    <repeat>
        <when value="MORN"/>
    </repeat>
</timing>
<additionalInstruction>
    <coding> 
        <system value="http://snomed.info/sct"/> 
        <code value="1116481000001105"/> 
        <display value="With food"/> 
    </coding>
</additionalInstruction>
```

**as needed with or after food**

```xml
<!-- as needed - with or after food -->
<asNeededBoolean value="true" />
<additionalInstruction>
    <coding> 
        <system value="http://snomed.info/sct"/> 
        <code value="311504000"/> 
        <display value="With or after food"/> 
    </coding>
</additionalInstruction>
```

### Sub-elements: `dayOfWeek` and `timeOfDay`

A dosage instruction can specify days of a week and/or specific times within a day for administration.

**on Monday and Thursday at 09:00 and 15:00**

```xml
<timing>
    <repeat>
        <dayOfWeek value="mon" />
        <dayOfWeek value="thu" />
        <timeOfDay value="09:00:00" />
        <timeOfDay value="15:00:00" />
    </repeat>
</timing>
```

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>FHIR Inconsistency</strong>: The FHIR R4 standard includes a comment that the elements <code>frequency</code>, <code>period</code> and <code>when</code> cannot be used with <code>dayOfWeek</code> and/or <code>timeOfDay</code>. However the rule defined in FHIR R4 only applies to <code>when</code> plus an example exists in the FHIR standard for "Daily at 10:00". Within FHIR R5, the comment has been amended to only apply to <code>when</code>. This guidance is based on the rules defined in FHIR R4 and latest ballot release of FHIR R5.
</div>

**Daily at 10:00**

```xml
<timing>
    <repeat>
        <frequency value="1"/>
        <period value="1"/>
        <periodUnit value="d"/>
        <timeOfDay value="10:00:00" />  
    </repeat>
</timing>
```

## Sub-element: `event`

A dosage instruction can specify specific dates and times for administration.

**on 1st Nov 2019**

```xml
<timing>
    <event value="2019-11-01" />
</timing>
```

**on 1st Nov 2019 at 10:30 and again on 1st Dec 2019 at 22:30**
```xml
<timing>
    <event value="2019-11-01T10:30" />
    <event value="2019-12-01T22:30" />
</timing>
```

### Sub-element: `code`

Allows a code, often a Latin abbreviation, for a timing schedule to be specified, for example: `BID` = twice a day 

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>Note:</strong> It is recommended that such codes are <strong>not</strong> used when the rest of the Dosage structure is supported by the system. Use the structures like frequency and period instead, so that a timing schedule can be computable.
</div>

---