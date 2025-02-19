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

Therefore it is recommended that the `patientInstruction` is **excluded** from any algorithmic construction of the `text` element - see [dose to text translation](DosetoTextTranslation).

Where there is a need to convey a text-based patient dosing instruction as (this a fictitious example), "*swallow while hopping on one leg*", then use a text-based `additionalInstruction`. The instruction should then be included within the `text` and only if different complete instructions are required for the patient would a `patientInstruction` be required.

```xml
<text value="1 tablet - daily - swallow while hopping on one leg"/>
<timing>
    <repeat>
        <frequency value="1" />
        <period value="1" />
        <periodUnit value="d" />
    </repeat>
</timing>
<additionalInstruction>
    <text value="swallow while hopping on one leg"/>
</additionalInstruction>
<doseAndRate>
    <doseQuantity>
        <value value="1" />
        <unit value="tablet" />
        <system value="http://snomed.info/sct" />
        <code value="428673006" />
    </doseQuantity>
</doseAndRate>
```

The benefit of this element is when different dosage phrasing is required for the clinician and the patient. An example of this would be for medication like **Prednisolone**. A typical dosing instruction for a clinical would be "30 milligram - daily - for 5 days". However for a patient this would typically be expressed as "6 tablets - daily - for 5 days".

```xml
<MedicationRequest>
    <medicationCodeableConcept>
        <coding>
            <system value="https://dmd.nhs.uk" />
            <code value="42087311000001104" />
            <display value="Prednisolone 5mg tablets" />
        </coding>
    </medicationCodeableConcept>
    <!-- other MedicationRequest elements -->
    <dosageInstruction>
        <text value="30 milligram - daily - for 5 days"/>
        <patientInstruction value="6 tablets - daily - for 5 days"/>
        <timing>
            <repeat>
                <frequency value="1" />
                <period value="1" />
                <periodUnit value="d" />
                <boundsDuration>
                    <value value="5" />
                    <unit value="day" />
                    <system value="http://unitsofmeasure.org" />
                    <code value="d" />
                </boundsDuration>
            </repeat>
        </timing>
        <doseAndRate>
            <doseQuantity>
                <value value="6" />
                <unit value="tablet" />
                <system value="http://snomed.info/sct" />
                <code value="428673006" />
            </doseQuantity>
        </doseAndRate>
    </dosageInstruction>
    <dispenseRequest>
        <quantity>
            <value value="30" />
            <unit value="tablet" />
            <system value="http://snomed.info/sct" />                       <code value="428673006" />
        </quantity>
        <!-- other dispenseRequest elements -->
    </dispenseRequest>
</MedicationRequest>
```

If `patientInstruction` is omitted, patient-facing use cases should present the string representation of the completed dosage as defined within `text`.

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>Note:</strong>
The <code>patientInstruction</code> element is <strong>not</strong> intended to provide instructions for a medication dispensing label.
</div>

---