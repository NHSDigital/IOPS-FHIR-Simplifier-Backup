## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle optional" title="Optional"></span> Optional


<h5><ins>Guidance</ins></h5>

This guidance currently relies on MESH as the sending mechanism and, as such, harnesses the MESH .CTL `<version>` element to indicate the version of the document that is being sent.

However, it is recommended that the `meta.versionId` element be populated with the version of the document that is being sent. This will be the same version as that populated in the the MESH .CTL file.

<h5><ins>Example</ins></h5>

```xml
<meta>
    <versionId value="1" />
</meta>
```

---