## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle required" title="Required"></span> Required

<h5><ins>Guidance</ins></h5>

URL to retrieve the document, this **MUST** be populated when the document is available. This **MUST** contain the full URL to the Binary resource, including when the DocumentReference is being included in an Access Record Structured Bundle.

<h5><ins>Example</ins></h5>

```xml
<content>
    <attachment>
      <url value="http://example.org/xds/mhd/Binary/07a6483f-732b-461e-86b6-edb665c45510" />
    </attachment>
</content>
```

---