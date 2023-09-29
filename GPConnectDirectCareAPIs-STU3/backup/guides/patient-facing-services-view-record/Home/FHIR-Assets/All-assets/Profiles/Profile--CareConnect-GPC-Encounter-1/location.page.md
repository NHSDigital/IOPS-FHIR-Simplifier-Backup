## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle required" title="Required"></span> Required


<h5><ins>Guidance</ins></h5>

This element references an instance of the `Location` profile which provides more detail on where the consultation or encounter took place - for example, a branch surgery.

It is expected that both `Location.status` and `Location.period` will not used.

<i class="fa fa-link"></i> {{pagelink:Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-GPC-Location-1}}

<h5><ins>Example</ins></h5>

```xml
<location>
    <location>
        <reference value="location-pp912334" />
    </location>
    <status>
        <coding>
            <system value="http://hl7.org/fhir/encounter-location-status" />
            <code value="active" />
            <display value="Active" />
        </coding>
    </status>
    <period>
        <start value="2022-10-28T13:38:00+00:00" />
        <end value="2022-10-28T13:53:00+00:00" />
    </period>
</location>
```

---