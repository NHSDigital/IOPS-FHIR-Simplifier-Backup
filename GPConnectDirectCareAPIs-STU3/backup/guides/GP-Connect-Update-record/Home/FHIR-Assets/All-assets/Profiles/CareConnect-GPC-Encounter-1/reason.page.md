## {{page-title}}

<h5><ins>Guidance</ins></h5>

`reason` **SHOULD** be populated for this capability. It is expected to include a SNOMED code rather than free text

<h5><ins>Example</ins></h5>

```xml
<reason>
    <coding>
        <system value="http://snomed.info/sct" />
        <code value="271681002" />
        <display value="Upset Stomach" />
    </coding>
</reason>
```

---