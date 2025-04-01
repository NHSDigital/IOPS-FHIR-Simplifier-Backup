## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle required" title="Required"></span> Required

<h5><ins>Guidance</ins></h5>

#### For investigations

A human readable explanation from the requesting healthcare professional containing an explanation on why the test has been requested and any contextual information they considered relevant.

#### For diary entries

Free text narrative to describe the reason for the diary entry or the action / activity required by the diary entry. This is for additional content beyond the `code` and `reasonCode` coded elements and is not intended to duplicate the content of those elements.

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