## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle required" title="Required"></span> Required

<h5><ins>Guidance</ins></h5>

This is the current organisation, as addressed by ODS code in the base URL, and NOT the patient’s registered practice which may be different.

This is the patient’s usual GP, if they have one and references the `Organization` within the bundle.

<h5><ins>Example</ins></h5>

```xml
<managingOrganization>
    <reference value="Organization/1"/>
</managingOrganization>
```

---