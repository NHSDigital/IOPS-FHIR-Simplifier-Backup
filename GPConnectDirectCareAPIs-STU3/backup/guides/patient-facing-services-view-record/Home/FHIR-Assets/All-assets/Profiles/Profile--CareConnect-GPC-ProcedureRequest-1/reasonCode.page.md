## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle required" title="Required"></span> Required


<h5><ins>Guidance</ins></h5>

An explanation or justification for why this diagnostic investigation is being requested in coded or textual form.

<h5><ins>Example</ins></h5>

```xml
<reasonCode>
    <coding>
        <system value="http://snomed.info/sct" />
        <code value="123823007" />
        <display value="Decreased blood oxygen pressure (finding)" />
        <snomedCT>
            <url value="https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-coding-sctdescid" />
            <extension>
            <valueId value="123823007" />
                <descriptionId value="123823007" />
                <descriptionDisplay value="Decreased blood oxygen pressure (finding)" />
            </extesion>
        </snomedCT>
    </coding>
    <text value="Decreased blood oxygen pressure (finding)" />
</reasonCode>
```

---