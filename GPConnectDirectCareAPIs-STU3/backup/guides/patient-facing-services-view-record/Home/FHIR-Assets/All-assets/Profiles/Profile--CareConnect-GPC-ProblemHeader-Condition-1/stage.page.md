## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle optional" title="Optional"></span> Optional

<h5><ins>Guidance</ins></h5>

This element **SHALL NOT** be populated.

Clinical stage or grade of a condition. May include formal severity assessments.

This `stage` element does not need to be populated.

<h5><ins>Example</ins></h5>

```xml
<stage>
    <summary>
        <coding>
            <system value="http://snomed.info/sct" />
            <code value="786005" />
            <display value="Clinical stage I B" />
        </coding>
    </summary>
    <assessment value="reference-clinicalimpression-or-diagnostic-report-or-observation--00298df" />
</stage>
```

---
