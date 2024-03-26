## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle required" title="Required"></span> Required


<h5><ins>Guidance</ins></h5>

Date when the allergy / intolerance first manifested. Currently restricted to values of `dateTime` for GP Connect.

This field **MUST** be populated where the GP system records an explicit onset date for an allergy.

<h5><ins>Example</ins></h5>

```xml
<onset>
    <onsetDateTime value="2011-05-07T00:00:00+00:00" />
</onset>
```

---