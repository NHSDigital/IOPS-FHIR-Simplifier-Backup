## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle optional" title="Optional"></span> Optional


<h5><ins>Guidance</ins></h5>

The `reason` element specifies the reason the encounter took place. A SNOMED code is preferred.


<h5><ins>Example</ins></h5>

```xml
<reason>
    <coding>
        <system value="http://snomed.info/sct" />
        <code value="1685005" />
        <display value="Rat bite fever" />
    </coding>
</reason>
```

---