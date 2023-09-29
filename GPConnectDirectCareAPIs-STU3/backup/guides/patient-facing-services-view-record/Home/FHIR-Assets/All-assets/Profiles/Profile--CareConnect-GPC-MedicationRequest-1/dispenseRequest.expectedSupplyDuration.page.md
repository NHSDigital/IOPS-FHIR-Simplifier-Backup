## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle required" title="Required"></span> Required

<h5><ins>Guidance</ins></h5>

Number of days' supply per dispense.


<h5><ins>Example</ins></h5>

```xml
<dispenseRequest>
    ...
    <expectedSupplyDuration>
        <value value="7" />
        <unit value="d" />
        <system value="http://unitsofmeasure.org" />
        <code value="d" />
    </expectedSupplyDuration>
    ...
</dispenseRequest>
```

---