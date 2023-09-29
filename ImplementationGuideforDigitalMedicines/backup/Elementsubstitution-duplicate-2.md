## Element: `substitution` <span class="mro-circle required" title="Required"></span>

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
    It is recommended this element is required for an MVP implementation.
</div>

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>Note:</strong> If omitted or has a value of <code>false</code> then substitution has not occured.
</div>

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>Important:</strong> A suitable definition and example use-cases for a <code>substitution</code> need to be defined.
</div>

**For example:**

<!-- would only occur in dose-based if specifically asked -->
- Is a sugar-free variant classed as a `substitution`?

<!-- dose based - wouldn't unless specified -->
- Is a generic variant of a drug classed as a `substitution`?

<!-- interesting one - need clinical support with this - e.g. do we throw away / process? -->
- Can a `substitution` be an entirely different medication, or should it be a new request?

- Should a <code>substitution</code> only be used, for example, if supplied in a different strength than requested?

---