## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle mandatory" title="Mandatory"></span> Mandatory


<h5><ins>Guidance</ins></h5>

A reference to the practitioner who administered and / or recorded the vaccine.

Where there is only a single practitioner recorded against the immunisation record:

- if the practitioner recording the vaccination also administered it (or intended to), then associate a `practitioner.role` code `AP` (Administering Provider) with practitioner profile
- if the GP Clinical System cannot determine whether the practitioner administered the vaccine or just recorded the vaccination event or both, then do not return a `practitioner.role`

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>Note</strong>: This is mandatory where the <code>practitioner.role</code> is populated.
</div>

<i class="fa fa-link"></i> {{pagelink:Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-GPC-Practitioner-1}}

<h5><ins>Example</ins></h5>

```xml
<practitioner>
    <actor>
        <reference value="practitioner-9093012" />
    </actor>
</practitioner>
```

---