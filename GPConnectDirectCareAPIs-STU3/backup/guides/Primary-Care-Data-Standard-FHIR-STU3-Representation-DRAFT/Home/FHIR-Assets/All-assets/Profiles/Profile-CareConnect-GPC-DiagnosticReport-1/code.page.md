## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle mandatory" title="Mandatory"></span> Mandatory


<h5><ins>Guidance</ins></h5>

It is expected in most cases, and in particular within the Access Record: Structured capability, that the value for the `code` element will be:

<i class="fa fa-link"></i> [721981007 | Diagnostic studies report (record artifact) |](https://termbrowser.nhs.uk/?perspective=full&conceptId1=721981007)


<h5><ins>Example</ins></h5>

```xml
<code>
    <coding>
        <display value="Diagnostic studies report (record artifact)" />
        <code value="721981007" />
        <system value="http://snomed.info/sct" />
        <snomedCT>
            <url value="https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-coding-sctdescid" />
            <extension>
            <valueId value="721981007" />
                <descriptionId value="721981007" />
                <descriptionDisplay value="Diagnostic studies report (record artifact)" />
            </extesion>
        </snomedCT>
    </coding>
    <text value="Diagnostic studies report (record artifact)" />
</code>
```

---