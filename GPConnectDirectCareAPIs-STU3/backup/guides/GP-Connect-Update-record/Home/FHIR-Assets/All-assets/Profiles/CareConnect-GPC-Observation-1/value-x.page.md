## {{page-title}}

<h5><ins>Guidance</ins></h5>

The value of the observation. This may be in any of the forms defined in the FHIR profile.

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>Note</strong>: The value <strong>MUST</strong> use the units specified as part of the FHIR vital signs specification.
</div>

<i class="fa fa-link"></i> [StructuredDefinition: observation-vitalsigns](https://build.fhir.org/vitalsigns.html)

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