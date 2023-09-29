## Element: `{{page-title}}`

### Sub-element: `Dosage.maxDosePerPeriod`

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    Used to define a maxiumum dose over a given time period.
</div>

An example would be a Sumatriptan 6mg injection which can be repeated after an hour but not again over a 24 hour period. The `maxDosePerPeriod` is defined as 12mg/24hours.

The `maxDosePerPeriod` is defined for each dosage instruction. For a multi-sequence instruction it would therefore be possible to define different maximum dosing periods within different sequences of the complete instruction.

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
    A real-world example of where this would be required has not yet been identified.
</div>

**Maximum dose per period of 12mg/24 hour**

```xml
<maxDosePerPeriod>
    <numerator>
        <value value="12"/>
        <unit value="milligram"/>
        <system value="http://unitsofmeasure.org"/>
        <code value="mg"/>
    </numerator>
    <denominator>
        <value value="24"/>
        <unit value="hour"/>
        <system value="http://unitsofmeasure.org"/>
        <code value="h"/>
    </denominator>
</maxDosePerPeriod>
```

---

### Sub-element: `Dosage.maxDosePerAdministration`

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    Used to define a maximum dose for a single administration.
</div>

An example would be Anagrelide for which a single dose should not exceed 2.5 mg. The `maxDosePerAdministration` is defined as 2.5mg.

In many scenarios it is expected that the `dosage.doseRange` would be used instead of `maxDosePerAdministration`.

The `maxDosePerAdministration` is defined for each dosage instruction. For a multi-sequence instruction it would therefore be possible to define different maximum dose administrations within different sequences of the complete instruction. 

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
    A real-world example of where this would be required has not yet been identified.
</div>


**Maximum dose per administration of 2.5mg**

```xml
<maxDosePerAdministration>
    <value value="2.5"/>
    <unit value="milligram"/>
    <system value="http://unitsofmeasure.org"/>
    <code value="mg"/>
</maxDosePerAdministration>
```

### Sub-element: `Dosage.maxDosePerLifetime`

<div class="callout-box--info">
    Used to define the maximum cumulative dose over the lifetime of a patient.
</div>

An example would be Daunorubicin which may have a maximum cumulative dose of 600mg/m2 (based on the size of the patient). The `maxDosePerLifetime` is defined as 600 mg/m2.

The `maxDosePerLifetime` can be defined for each dosage instruction; which, for a multi-sequence instruction is illogical, as any `maxDosePerLifetime` is equally applicable to all dosage sequence that relate to the single medication coded concept.

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>Note:</strong> If a <code>maxDosePerLifetime</code> statement is required with a multi-sequence instruction, it is recommended to define it within the last / final sequence to ensure that the information is presented at the end of a the complete instruction, rather than th middle which could be overlooked.
</div>


**Maximum dose over lifetime of the patient of 600 mg/m2**

```xml
<maxDosePerLifetime>
    <value value="600"/>
    <unit value="milligram per square metre"/>
    <system value="http://unitsofmeasure.org"/>
    <code value="mg/m2"/>
</maxDosePerLifetime>
```