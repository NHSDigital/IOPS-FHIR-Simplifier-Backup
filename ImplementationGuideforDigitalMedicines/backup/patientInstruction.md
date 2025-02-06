## Element: `{{page-title}}`

FHIR defines as "Instructions in terms that are understood by the patient or consumer".

It is good practice that this element contains the complete dosage instruction as a text string, in terms that are understood by the patient or consumer. This includes those prescriptions that the patient may not see or will not self administer, for example, during inpatient care. 

There may be occurrences when dosage instructions are designed to be administered only by a healthcare professionals (e.g. IV dosage). In these instances the `patientInstruction` may be omitted. 

It would be expected that in many cases `patientInstruction` will contain the same dose string as `text`. 

```xml
<text value="2 tablet - 4 times a day - at a meal - Dissolve or mix with water before taking - up to a maximum of 12 tablets in 24 hours"/>
<!-- other Dosage elements -->
<patientInstruction value="2 tablet - 4 times a day - at a meal - Dissolve or mix with water before taking - up to a maximum of 12 tablets in 24 hours"/>
```
The benefit of this element is when different dosage phrasing is required for the clinician and the patient. A real-world example for this use case will be added in a future version of this guidance.

If `patientInstruction` is omitted, patient-facing use cases should present the string representation of the completed dosage as defined within `text`.

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>Note:</strong>
The <code>patientInstruction</code> element is <strong>not</strong> intended to provide instructions for a medication dispensing label.
</div>

---