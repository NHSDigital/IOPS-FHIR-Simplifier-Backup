## Timing Elements: `when`, `offset`, `dayOfWeek`, `timeOfDay`, `event` and `code`

A dosage instruction can be tied to the specific days, dates and times, plus life events related to eating or sleeping.

### Sub-elements: `when` and `offset`

The [when](http://hl7.org/fhir/stu3/datatypes-definitions.html#Timing.repeat.when) element ties to the regular life events of sleeping and eating, for example:

- `C` = event occurs at a meal
- `WAKE` = event occurs `[offset]` after waking

An offset allows the event to be tied `x` minutes before or after. 

The offset is an unsigned integer value so different codes within the when value-set are used to define before or after.

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>Note:</strong> Guidance for the use of timing codes for <code>event occurs before/at/after a meal</code> is currently under review and may be subject to change.
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

Multiple `when` statements can be used, such as:

**Event occurs at or after a meal**

```xml
<timing>
    <repeat>
        <when value="C"/>
        <when value="PC"/>
    </repeat>
</timing>
```

<!--
to add;
something about assumpton of 3 meals. day
+ caveats
where you have a coded meal it is recommended to include timing instructions such as a frequency.
Example row 82
-->
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
    <strong>FHIR  Inconsistency</strong>: The FHIR R4 standard includes a comment that the elements <code>frequency</code>, <code>period</code> and <code>when</code> cannot be used with <code>dayOfWeek</code> and/or <code>timeOfDay</code>. However the rule defined in FHIR R4 only applies to <code>when</code> plus an example exists in the FHIR standard for "Daily at 10:00". Within FHIR R5, the comment has been amended to only apply to <code>when</code>. This guidance is based on the rules defined in FHIR R4 and latest ballot release of FHIR R5.
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
    <strong>Note:</strong> It is recommended that such codes are not used when the rest of the Dosage structure is supported by the system. Use the structures like frequency and period instead, so that a timing schedule can be computable.
</div>

---