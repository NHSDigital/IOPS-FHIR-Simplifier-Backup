## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle required" title="Required"></span> Required

<h5><ins>Guidance</ins></h5>

A reference to a `CareConnect-GPC-Practitioner-1` profile, representting the clinician responsible for making the obsersvation.

Where the observation was performed at another organisation, then a reference to a `CareConnect-GPC-Organization` **MUST** be populated in the `performer` element. This will be in addition to the clinical practitioner, if both are available.

If neither the performing organisation, or the clinical practitioner are known, then this **MUST** be populate with the details of the person who recorded teh data into the system.

<h5><ins>Example</ins></h5>

```xml
<context>
    <reference value="practitioner-9090arke3" />
    <reference value="organization-0012sa2k" />
</context>
```

---