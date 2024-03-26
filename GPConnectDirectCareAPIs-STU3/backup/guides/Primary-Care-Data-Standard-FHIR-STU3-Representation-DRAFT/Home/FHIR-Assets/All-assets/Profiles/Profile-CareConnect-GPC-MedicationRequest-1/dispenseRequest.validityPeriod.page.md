## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle mandatory" title="Mandatory"></span> Mandatory

<h5><ins>Guidance</ins></h5>

Prescription start and end dates.

Start date is mandatory. Where there is a defined expiry or end date the end date MUST be supplied.

**For MedicationRequest instances where intent is set to plan:**

- This refers to the period that the medication/medical device plan is active.
- This MUST mirror `MedicationStatement.effective`


**For MedicationRequest instances where intent is set to order:**

- This refers to the period that the issued prescription is active

**Period.start is MANDATORY**

Use one of the following dates in order of descending preference:

- The prescription issue date recorded in the patient record
- The date the prescription was recorded.


**Period.end is OPTIONAL**

Use one of the following dates in order of descending preference:

- The prescription end date recorded in the patient record
- The prescription end date derived from `Period.start` and the duration
- The `Period.start` date -- This option should only occur where data has been lost (for example, during the record transfer between two systems) and is used to ensure that an ended prescription will always have an end date.

<h5><ins>Example</ins></h5>

```xml
<dispenseRequest>
    ...
    <validityPeriod>
        <start value="2023-01-20" />
        <end value="2023-01-27" />
    </validityPeriod>
    ...
</dispenseRequest>
```