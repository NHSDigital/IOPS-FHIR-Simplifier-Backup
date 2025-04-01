## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle required" title="Required"></span> Required


<h5><ins>Guidance</ins></h5>

The `reasonCode` element can be populated with the source system’s main coded entry for the referral.

Additional, coded or text entries which are clearly captured as reasons for referral may also be included.

<h5><ins>Example</ins></h5>


```xml
<reasonCode>
    <coding>
        <system value="http://snomed.info/sct" />
        <code value="195967001" />
        <display value="Asthma (disorder)" />
    </coding>
</reasonCode>
```

---