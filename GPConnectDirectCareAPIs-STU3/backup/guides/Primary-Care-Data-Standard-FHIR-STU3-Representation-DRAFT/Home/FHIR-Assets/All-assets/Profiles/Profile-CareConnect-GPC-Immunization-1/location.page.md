## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle required" title="Required"></span> Required


<h5><ins>Guidance</ins></h5>

The GP practice, branch surgery or other location where the vaccination occurred or was intended to occur, if known.

If the immunisation record in the GP Clinical System does not record a location for the vaccination, but is linked to a consultation then

- if the vaccine was administered or was intended to be administered during the consultation the location **MUST** be populated with the location of the consultation
- if the vaccine was **NOT** administered or intended to be administered during the consultation and the location for the vaccination is therefore unknown, then a location **MUST** be absent

<i class="fa fa-link"></i> {{pagelink:Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-GPC-Location-1}}

<h5><ins>Example</ins></h5>

```xml
<location>
    <reference value="location-992891" />
</location>
```

---