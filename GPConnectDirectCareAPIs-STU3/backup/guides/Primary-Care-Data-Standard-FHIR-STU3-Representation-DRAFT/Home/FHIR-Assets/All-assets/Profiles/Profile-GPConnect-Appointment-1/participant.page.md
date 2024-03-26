## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle mandatory" title="Mandatory"></span> Mandatory

<h5><ins>Guidance</ins></h5>

The participants involved in the appointment including the `Location`, `Practitioner` and `Patient`.

<h5><ins>Example</ins></h5>

```xml
<participant>
    <actor>
        <reference value="Patient/1"/>
    </actor>
    <status value="accepted"/>
</participant>
<participant>
    <actor>
        <reference value="Practitioner/2"/>
    </actor>
    <status value="accepted"/>
</participant>
<participant>
    <actor>
        <reference value="Location/1"/>
    </actor>
    <status value="accepted"/>
</participant>
```

---