## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle required" title="Required"></span> Required

<h5><ins>Guidance</ins></h5>

Who and/or what authored the document.

* <i class="fa fa-link" aria-hidden="true"></i> {{pagelink:Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-GPC-Practitioner-1}}
* <i class="fa fa-link" aria-hidden="true"></i> {{pagelink:Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-GPC-Patient-1}}
* <i class="fa fa-link" aria-hidden="true"></i> {{pagelink:Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-GPC-RelatedPerson}}

The free text field MUST be present

<h5><ins>Example</ins></h5>

```xml
<note>
    <author>
        <reference value="practitioner-948392" />
    </author>
    <time value="2022-10-13T16:59:00Z" />
    <text>
        "Free text...".
    </text>
</note>
```

---