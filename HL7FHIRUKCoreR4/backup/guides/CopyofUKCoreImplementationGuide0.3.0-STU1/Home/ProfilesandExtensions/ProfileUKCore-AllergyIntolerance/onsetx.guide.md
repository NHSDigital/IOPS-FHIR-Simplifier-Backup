## `onset[x]`

Record of the date and/or time of the onset of the reaction caused by the allergy or intolerance which can be recorded in one of five ways;
- `onsetDateTime`
- `onsetAge`
- `onsetPeriod`
- `onsetRange`
- `onsetString`.

### Provider Systems

Provider systems are recommended to support at least `onsetDateTime` and `onsetAge` where this date is available.

It is recommended **not** to record the onset using an `onsetPeriod` or `onsetRange` as these data types are complex and less useful. If the exact onset date is not known, but was between two known dates, e.g. 2018 and 2019, then use the lower/older date as the `onsetDateTime` instead of using an `onsetPeriod`.

It is recommended **not** to record the onset using an `onsetString` as this data will not be machine processable.

### Consumer Systems

Consumer systems **MUST** be able to handle any of the `onset` data types.

---
