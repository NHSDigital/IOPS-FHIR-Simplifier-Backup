## {{page-title}}

### Element: `method`

No additional formatting required.

---

### Element: `doseAndRate.doseQuantity`

Express as:

> \{quantity\} \{units\}

- 50 milligram

- 2 tablets

---

### Element: `doseAndRate.doseRange`

Express as:

> \{low\} to \{high\} \{high_units\}

- 20 to 40 millilitre

Where only a `doseRange.high` is defined, express as:

> up to \{high\} \{high_units\}

- up to 40 millilitre

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>Note:</strong> It would be clinically unsafe to express a <code>doseRange</code> with only a <code>low</code> value and an omitted <code>high</code> value.
</div>

---


### Element: `doseAndRate.rateRatio`

When the denominator value is 1 (one) express a `rateRatio` as:

> at a rate of \{numerator_value\} per \{denominator_unit\}

Otherwise express as:

> at a rate of \{numerator_value\} every \{denominator_value\} \{denominator_unit\}

Express the time-based units in plural when required.

- at a rate of 30 millitre per hour

- at a rate of 30 millitre every 2 hours

---

### Element: `doseAndRate.rateRange`

Express as:

> at a rate of \{low_value\} to \{high_value\} \{high_units\}

- at a rate of 1 to 2 liter per minute

---

### Element: `doseAndRate.rateQuantity`

Express as:

> at a rate of \{value\} \{units\}

- at a rate of 1 microgram per kilogram per hour 

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>Note:</strong> The above example uses the UCUM unit <code>microgram per kilogram per hour</code>.
</div>

---

### Elements: `duration` / `durationMax`

Express a `duration` as: 

> over \{value\} \{units\}.

Express the time-based units in plural when required.

Where a `durationMax` is defined, append with 

> (maximum \{max_value\} \{max_units\}).

- over 8 hours

- over 4 hours (maximum 6 hours)

---

### Elements: `frequency` / `frequencyMax` / `period` / `periodMax`

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>Note:</strong> Logic to produce human readable timing instructions is complex with both generic rules and a number of special cases.
</div>

Express the combination of `frequency` and `period` as:

> \{frequency\} times every \{period_value\} \{period_unit\}`

- 3 times every 8 hours


Where a `frequencyMax` is defined, express as:

> \{frequency\} to \{frequencyMax\} times every \{period_value\} \{period_unit\}

- 2 to 3 times every 8 hours


Where a `periodMax` is defined, express as:

> \{frequency\} times every \{period_value\} to \{periodMax_value\} \{period_unit\}

- 3 times every 6 to 8 hours


Where both `frequencyMax` and `periodMax` are defined, express as:

> \{frequency\} to \{frequencyMax\} times every \{period_value\} to \{periodMax_value\} \{period_unit\}

- `2 to 3 times every 6 to 8 hours`


Where a `frequencyMax` is defined without a `frequency` then express as:

> up to \{frequencyMax\} times

- up to 3 times a day

- up to 4 times every 8 hours

- up to 6 times every 3 to 4 weeks

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>Note:</strong> The omission of both a <code>frequency</code> and <code>frequencyMax</code> when either a <code>period</code> or <code>periodMax</code> is present is allowed as per cardinality rules but should be prevented in practice as does not result in a logical timing instruction. 
</div>

---

#### Special Cases

When `period` is 1 (one) without a `frequency`, express as:

> daily, weekly, monthly, or annually _depending on the `periodUnit`_.

In theory, the `periodUnit` could be `s` (seconds) or `min` (minutes); however, the use of these without an associated `frequency` is illogical.

When `frequency` is 1 (one) without a `period`, express as:

> once

When `frequency` is 2 (two) defined without a `period`, express as:

> twice

When `frequency` is greater than 2 (two) and defined without a `period`, express as:

> \{frequency\} times

- 3 times

When `frequency` and `period` are both 1 (one) express as:

> once a \{period_unit\}.

- once a week

When `frequency` is 1 (one) and `period` is greater than 1 (one) express as:

> every \{period_value\} \{period_unit\}

or 

> every \{period_value\} to \{periodMax_value\} \{period_unit\}

- every 8 hours

- every 6 to 8 hours


When `frequency` is 2 (two) and `period` is 1 (one) express as:

> twice a \{unit\}.

- twice a day

When `frequency` is greater than 2 (two) and `period` is 1 (one) express as:

> \{frequency\} times a \{unit\}.

- 4 times a day

When `frequency` is 2 (two) and `period` is greater than 1 (one) express as:

> twice every \{period_value\} \{period_unit\}

or 

> twice every \{period_value\} to \{periodMax_value\} \{period_unit\}

- twice every 8 hours

- twice every 6 to 8 hours

---

### Elements: `offset` / `when`

Any `offset` will be defined as a number of minutes. If this equates to a whole number of hours or days then express as the number of hours (=60 minutes) or days (=1440 minutes). Use the singular or plural expression of time when required. Separate multiple statements with a comma and use the word "` and `" to separate the final two statements.

The FHIR [event timing value-set](http://hl7.org/fhir/stu3/valueset-event-timing.html) used for `when` should have descriptions modified to make them more human readable. 

Remove the text "event occurs [offset]" and "(from the Latin...)" from the descriptions.

Simplify the following value-set definitions;

 * Display: "After Sleep" - Use definition "once asleep"
 * Display: "HS" - Use definition "before sleep"
 * Display: "WAKE" - Use definition "upon waking"
 * Display: "C" - Use Definition "at a meal" 
 * Display: "CM" - Use Definition "at breakfast" 
 * Display: "CD" - Use Definition "at lunch" 
 * Display: "CV" - Use Definition "at dinner"

Express as:

> \{offset_value\} minute(s) / hour(s) / day(s) \{modified_when_value-set\}

- at breakfast

- 30 minutes before a meal

- 1 hour before sleep

- 2 hours after breakfast

- in the morning and in the evening

- at night

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>Note:</strong>
    The valueset for <code>event.timing</code> suggests using the <i>during</i> preposition, which differs to the examples above.
    <br/>
    Prepositions are interchangeble in the English language (e.g. <code>during</code>,  <code>in</code> or <code>at</code>), and care should be taken to ensure that the appropriate preposition is used in the dosage instruction, for the person administering the medication.
</div>

---

### Element: `dayOfWeek`

Express as:

> on \{dayOfWeek\} 

using the full description from the FHIR value-set, i.e. `mon` = "`Monday`". 

Separate multiple statements with a comma and use the word "` and `" to separate the final two statements.

- on Monday

- on Monday, Wednesday and Friday

---

### Element: `timeOfDay`

Express as:

> at \{timeOfDay\}

Separate multiple statements with a comma and use the word "` and `" to separate the final two statements. If a time is expressed with `:00` seconds then express just in terms of hours and minutes. Sending systems should always provide times using the 24 hour clock. 

Receiving systems may apply local preferences for display, i.e. `15:00` or `3:00pm`.

- at 10:00

- at 10:00 and 15:00

---

### Element: `route`

No additional formatting required.


---

### Element `site`

No additional formatting required.

---

### Elements: `asNeededCodeableConcept` / `asNeeded`

Express the `asNeededBoolean` statement as:

> as required

Express the `asNeededCodeableConcept` as:

> as required for \{coded_value_description\}

- as required for Migraine

---

### Elements: `boundsDuration` / `boundsRange`

Express the units in plural when required.

Express `boundsDuration` as:

> for \{value\} \{units\}. 

- for 7 days

Express `boundsRange` as:

> for \{low\} to \{high\} \{high_units\}

- for 2 to 4 hours

Where only `boundsRange.low` is defined, express as:

> for at least \{low\} \{low_units\}

- for at least 2 hours

Where only `boundsRange.high` is defined, express as:

> for up to \{high\} \{high_units\}

- for up to 2 hours

---

### Elements: `count` / `countMax`

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>Note:</strong>
The most appropriate use of English to express a <b>count</b> may vary between use cases. This guidance suggests the phrasing <code>take X times</code> but a phrasing of <code>take x doses</code> or <code>use X times</code> may be preferrable for some use cases. 
</div>

If `count` is 1 (one) then express as:

> take once 

If `count` is 2 (two) then express as:

> take twice

Otherwise express `count` as:

> take \{count\} times

Where a `countMax` is defined, insert with:

> to \{countMax\}

- take once

- take twice

- take 3 times

- take 3 to 5 times

---

### Element: `event`

Express `event` statements as:

> on \{event_value\}

Separate multiple statements with a comma and use the word " and " to separate the final two statements. 

Local preferences can be used to display the date in `dd/mm/yyyy` or `dd-mmm-yyyy` format.

- on 25/01/2019

- on 25-Jan-2019

- on 25/01/2019, 25/02/2019 and 25/03/2019

---

### Elements: `maxDosePerPeriod` / `maxDosePerAdministration` / `maxDosePerLifetime`

Express a `maxDosePerPeriod` statement as:

> up to a maximum of \{numerator_value\} \{numerator_unit\} in \{denominator_value\} \{denominator_unit\}
Express the time-based units in plural when required.

- up to a maximum of 1000 milligram in 24 hours


Express a `maxDosePerAdministration` statement as:

> up to a maximum of \{value\} \{unit\} per dose

- up to a maximum of 2 milligram per dose


Express a `maxDosePerLifetime` statement as:

> up to a maximum of \{value\} \{unit\} for the lifetime of patient

- up to a maximum of 60 milligram for the lifetime of patient

---

### Element: `additionalInstruction`

Separate multiple statements with a comma and use the word "` and `" to separate the final two statements.

- Do not stop taking this medicine except on your doctor's advice

- Dissolve or mix with water before taking `and` Contains aspirin

---

### Element: `patientInstruction`

Excluded from the algorithm.

~~No additional formatting required.~~

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
UPDATE FEB 2025. The element <code>patientInstruction</code> has been removed from this guidance as it's contents would often duplicate what is contained within <code>text</code>. See <a href="ElementDosage?version=current#additionalInstruction">patientInstruction</a> for more info.
</div>

---

## Multi-Sequence Instructions

When a complete dosing instruction is described by multiple `Dosage` elements, the translated dose strings can be concatinated.

### Sequential Instructions

Separate sequential instructions (where each `sequence` has an incremental value) can be concatinated separated by `, then `.

- Anydrug - 50 milligram - once a day - oral - for 1 week`, then ` 100 milligram - once a day - oral - for 3 weeks

### Concurrent  Instructions

Separate parallel instructions (where `sequence` has the same value) can be concatinated separated by `, and `.

- Anydrug - 50 milligram - once a day - in the morning - oral`, and `100 milligram - once a day - in the evening

---