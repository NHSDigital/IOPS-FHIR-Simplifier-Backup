## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle required" title="Required"></span> Required


<h5><ins>Guidance</ins></h5>

All notes that are associated with this medication/medical device record.

Sometimes labelled Pharmacy text or instructions for pharmacy.

<h5><ins>Example</ins></h5>

```xml
<note>
    <authorReference>
        <identifier>
            <system value="https://fhir.hl7.org.uk/Id/gmc-number" />
            <value value="00143922" />
        </identifier>
    </authorReference>
    <time value="2023-01-20T10:47:35.0536208+00:00" />
    <text value="Free text... R4 of the FHIR standard supports GitHub Flavoured Markdown (GFM)" />
</note>
```

---