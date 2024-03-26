## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle optional" title="Optional"></span> Optional

<h5><ins>Guidance</ins></h5>

### For structural list use only

The `note` element can be used to provide any comments regarding the list.

The text versions of any warning messages included with the list. Where there are multiple warning messages their text is concatenated.

<h5><ins>Example</ins></h5>

```xml
<note>
    <author>
        <reference value="practitioner-0019asb" />
    </author>
    <time value="2022-11-01T11:29:00Z" />
    <text>
        Free text... R4 of the FHIR standard supports GitHub Flavoured Markdown (GFM).
    </text>
</note>
```

---