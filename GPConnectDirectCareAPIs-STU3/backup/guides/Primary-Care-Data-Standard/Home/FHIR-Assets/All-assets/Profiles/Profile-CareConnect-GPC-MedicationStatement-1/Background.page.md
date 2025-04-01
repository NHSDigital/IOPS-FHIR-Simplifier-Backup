## {{page-title}}

### What is a MedicationStatement?

A `MedicationStatement` (despite the potentially confusing name) is not a statement in the traditional sense of a list of items (such as bank statement), and in FHIR R5 it is going to be renamed to `MedicationUsage`.

The definition of a `MedicationStatement` from hl7.org is as follows:

> A record of a medication that is being consumed by a patient. A MedicationStatement may indicate that the patient may be taking the medication now, or has taken the medication in the past or will be taking the medication in the future.

A `MedicationStatement` resource will contain **a single line-item** of medication, and _may contain_ information from the original `MedicationRequest`, `MedicationDispense` or `MedicationAdministration` if the system populating the resource knows about them.

It is possible; however, to create the resource **without** this information.

### Example

In the diagram below there are three active medications, one completed medication, and a stopped medication. 

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>Note</strong> that all of medications are derived from a <code>MedicationStatement</code> - each with varying data-sources.
</div>

<br />

{{render: medication-statement-illustration}}

<br />

### Potential data-sources for the `MedicationStatement` resource

- Pharmacy System - `MedicationRequest`
- Dispensing System - `MedicationDispense`
- Patient self-declared - `MedicationAdministration`
- ICS Shared Record - `MedicationStatement`

---