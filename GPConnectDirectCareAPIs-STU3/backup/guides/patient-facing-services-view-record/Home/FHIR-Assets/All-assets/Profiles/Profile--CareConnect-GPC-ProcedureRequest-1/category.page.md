## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle optional" title="Optional"></span> Optional


<h5><ins>Guidance</ins></h5>

A use-case for the `category` element within GP Connect has not been defined.

<h5><ins>Example</ins></h5>

```xml
<category>
    <coding>
        <system value="http://snomed.info/sct" />
        <code value="83474000" />
        <display value="Psychiatric commitment procedure (procedure)" />
        <snomedCT>
            <url value="https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-coding-sctdescid" />
            <extension>
            <valueId value="83474000" />
                <descriptionId value="83474000" />
                <descriptionDisplay value="Psychiatric commitment procedure (procedure)" />
            </extesion>
        </snomedCT>
    </coding>
    <text value="Psychiatric commitment procedure (procedure)" />
</category>
```

---