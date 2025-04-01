## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle optional" title="Optional"></span> Optional

<h5><ins>Guidance</ins></h5>

The name of the document. Where the document is a KOS document this field (designated typeCode) is used to carry the DICOM Imaging procedure: This attribute shall be populated by the XDS-I Imaging Document Source from a code in the Procedure Code Sequence (0008,1032) of the performed procedure with which the document is associated. Values may be found in a suitable DICOM browser

<h5><ins>Example</ins></h5>

```xml
<type>
    <coding>
        <display value="The name of the document" />
        <code value="824331000000106" />
        <system value="http://snomed.info/sct" />
    </coding>
</type>
```
---