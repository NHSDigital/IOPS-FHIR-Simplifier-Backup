## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle optional" title="Optional"></span> Optional

<h5><ins>Guidance</ins></h5>

### Individual Test Result

The general type of test result. A default value of `Laboratory` should be used if a more specific value is not available - for example, pathology, microbiology, and so on.

### Other use cases

This element is not used.

<h5><ins>Example</ins></h5>

```xml
<category>
    <coding>
        <system value="http://terminology.hl7.org/CodeSystem/observation-category" />
        <code value="vital-signs" />
        <display value="Vital Signs" />
    </coding>
</category>
```

---