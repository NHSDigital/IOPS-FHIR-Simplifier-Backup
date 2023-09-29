## Element: `identifier` <span class="mro-circle required" title="Required"></span>

For an `STU3` implementation record the patient’s NHS Number as an identifier.

- The `Patient.identifier.use` should be `official`
- The `Patient.identifier.type` should be `MR`
- The `Patient.identifier.value` must be the patient’s NHS Number
- The `Patient.identifier.period` can be omitted unless there is a known validity period for the NHS Number


For a `UK Core` implementation the `identifier (nhsNumber)` extension should be used for the patient’s NHS Number.

Additionally an implementation can populate an additional identifier to record any local patient identifier that is necessary for local business process interoperability.

---