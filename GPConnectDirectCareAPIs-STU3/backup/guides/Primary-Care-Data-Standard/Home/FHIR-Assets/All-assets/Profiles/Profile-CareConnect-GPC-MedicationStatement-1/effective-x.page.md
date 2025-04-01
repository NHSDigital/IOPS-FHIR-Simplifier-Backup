## {{page-title}}

<h5><ins>Usage (Conditional)</ins></h5>

<span class="mro-circle required" title="Required"></span> Required

<h5><ins>Guidance</ins></h5>

The period the medication or medical device is authorised under this medication/medical device plan. For items that are repeats and repeat dispensed this refers to the entire cycle of prescriptions made under the authorisation. For acutes, this refers to the period of the prescription issue.

This element is especially required when the `status` is `intended`.

Either:

- `effectiveDateTime` a date time at which the medication started or should start
- `effectivePeriod` the period over which the patient has taken or should take the medication

The use of `effectivePeriod` is to be preferred, and should start when the medication started in any preceding episode of care.

The date / time format allows various degrees of date resolution; year, year/month and exact date so an approximate date can be used when the exact date is not known.

This could be either backdated or future dated.

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <b>Note</b>: Where the end date is unknown it may be omitted.
</div>

<h5><ins>Examples</ins></h5>

```xml
<effectiveDateTime value="2022-09-23T09:04:00Z" />
```

```xml
<effectivePeriod>
    <start value="2022-09-23T09:04:00Z" />
    <end value="2022-09-30T23:59:59Z" />
</effectivePeriod>
```

---