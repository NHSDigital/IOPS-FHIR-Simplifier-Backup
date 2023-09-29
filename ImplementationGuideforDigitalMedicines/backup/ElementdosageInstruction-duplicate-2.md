## Element: `dosageInstruction` <span class="mro-circle required" title="Required"></span>

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
    It is recommended this element is required for an MVP implementation.
</div>

An example instance where this could be used is if a substitution has taken place where the dosage instruction differs to the one in the `MedicationRequest`.

If the `dosageInstruction` element is used then it should be represented as a structured dose where possible in the event that the receiving system is required to interpret the content.

In this instance, population of just the `dosageInstruction.text` element would be **unacceptable** for a successful implementation.

Refer to FHIR Dose Syntax Implementation Guidance (or any subsequent version) for guidance.

<a class="nhsd-a-button" target="_blank" href="https://simplifier.net/guide/dosesyntaximplementationguidanceforfhirr4">View the R4 FHIR Dose Syntax Guidance</a>

---