## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle optional" title="Optional"></span> Optional

<h5><ins>Guidance</ins></h5>

This element **SHALL NOT** be populated.

The subjective severity of the condition represented using SNOMED.

- [255604002 | Mild (qualifier value) |](https://termbrowser.nhs.uk/?perspective=full&conceptId1=255604002)
- [6736007 | Moderate (severity modifier) (qualifier value) |](https://termbrowser.nhs.uk/?perspective=full&conceptId1=6736007)
- [24484000 | Severe (severity modifier) (qualifier value) |](https://termbrowser.nhs.uk/?perspective=full&conceptId1=24484000)

<h5><ins>Example</ins></h5>

```xml
<severity>
    <coding>
        <system value="http://snomed.info/sct" />
        <code value="255604002" />
        <display value="Mild (qualifier value)" />
    </coding>
</severity>
```

---