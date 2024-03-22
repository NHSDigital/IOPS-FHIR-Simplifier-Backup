## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle required" title="Required"></span> Required

<h5><ins>Guidance</ins></h5>

### Individual Test Result

Provides a reason why the expected value in the element `Observation.value[x]` is missing.

<i class="fa fa-link"></i> [ValueSet: value-absent-reason](http://hl7.org/fhir/stu3/valueset-observation-valueabsentreason.html)

<h5><ins>Example</ins></h5>

```xml
<dataAbsentReason>
    <system value="http://hl7.org/fhir/ValueSet/observation-valueabsentreason" />
    <code value="unsupported" />
    <display value="Unsupported" />
</dataAbsentReason>
```

---