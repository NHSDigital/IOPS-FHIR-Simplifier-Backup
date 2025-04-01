## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle required" title="Required"></span> Required

<h5><ins>Guidance</ins></h5>

All text associated with the AllergyIntolerance including user-entered notes and qualifiers is grouped together and expressed in this field, which ensures unmapped coded values or qualifiers are not lost.

Must be used to contain any textual data relevant to the allergy.

<h5><ins>Example</ins></h5>

```xml
<note>
    <author>
        <reference value="practitioner-948392" />
    </author>
    <time value="2022-10-13T16:59:00Z" />
    <text>
        Free text... R4 of the FHIR standard supports GitHub Flavoured Markdown (GFM).
    </text>
</note>
```

---