## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle mandatory" title="Mandatory"></span> Mandatory

<h5><ins>Guidance</ins></h5>

### Test Group Header

The clinical code that represents the name of the test group - for example, Full blood count.

### Individual Test Result

The clinical code that represents the name of the test result or test analyte.

### Filing Comments

Fixed value of `37331000000100` for `Comment note`.

### Observations

The clinical code that represents the data within the observation.

For free text without any clinical code set to `37331000000100 Comment note`.

### Blood Pressure

The clinical code that represents the header or panel of the blood pressure.

Where there is an appropriate header code for a recognised triple recorded in the providing GP system this **MUST** be populated here.

If there is no header/panel code and only the code(s) for systolic and/or diastolic components are recorded, then this **MUST** be populated with the SNOMED codes conceptID ‘75367002’ and the descriptionID of the preferred term ‘125176019’ which has the description ‘Blood pressure’ and is an observable entity.

<h5><ins>Example</ins></h5>

```xml
<code>
    <coding>
        <system value="http://snomed.info/sct" />
        <code value="37331000000100" />
        <display value="Comment note (record artifact)" />
    </coding>
</code>
```

---