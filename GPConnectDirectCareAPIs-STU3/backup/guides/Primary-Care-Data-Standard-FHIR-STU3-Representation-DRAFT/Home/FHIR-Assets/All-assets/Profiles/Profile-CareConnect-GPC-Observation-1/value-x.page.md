## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle required" title="Required"></span> Required

<h5><ins>Guidance</ins></h5>

### Test Group Header

N/A

### Individual Test Result

The value of the test. This may be in the form of, but is not limited to, one of the following datatypes: a quantity, string or an attachment.

### Filing Comments

Where a ‘Test group’ or ‘Test result’ has been filed the value should match the code from the ‘Test group header’ or ‘Test result’ resource respectively.

### Observations

The value of the observation. This may be in any of the forms defined in the profile.

Where applicable the value **MUST** use the units specified as part of the [FHIR vital signs specification](https://www.hl7.org/fhir/observation-vitalsigns.html).

### Blood Pressure

N/A

<h5><ins>Example</ins></h5>

```xml
<valueQuantity>
    <value value="16" />
    <unit value="breaths per minute" />
    <system value="http://unitsofmeasure.org" />
    <code value="{resps}/min" />
</valueQuantity>
```

---