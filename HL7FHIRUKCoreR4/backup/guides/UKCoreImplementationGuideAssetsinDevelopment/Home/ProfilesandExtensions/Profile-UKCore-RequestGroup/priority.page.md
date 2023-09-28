## `{{page-title}}`

When `RequestGroup` is used for medication requests the recommendation is that `RequestGroup.priority` is not to be used within an implementation - or used with caution.

The stating of a priority, in any business context including healthcare, is often de-valued as given the choice, every clinician wants medication urgently for their patients.

If `RequestGroup.priority` is used, consider only initially supporting the routine and urgent request priorities, and set clear criteria for when a `MedicationRequest` and ` RequestGroup` should be marked and handled as urgent.
<br>
### Usage of the value "stat"

The `stat` request priority is potentially confusing as it has two meanings:

1. to indicate a "here and now" order going to pharmacy
2. used within a `MedicationRequest.dosageInstruction` can also mean "give once immediately".

Avoid using `stat` and `asap` where possible.

---
