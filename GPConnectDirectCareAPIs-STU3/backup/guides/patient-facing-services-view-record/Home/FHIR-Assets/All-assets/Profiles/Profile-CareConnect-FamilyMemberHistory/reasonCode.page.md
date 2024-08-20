## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle optional" title="Optional"></span> Optional


<h5><ins>Guidance</ins></h5>

The `reasonCode` describes why the family member history occurred in coded or textual form.

<h5><ins>Example</ins></h5>


```xml
<specialty>
    <coding>
        <system value="http://snomed.info/sct" />
        <code value="841002" />
        <display value="Congenital absence of skull bone" />
        <snomedCT>
            <url value="https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-coding-sctdescid" />
            <extension>
            <valueId value="841002" />
                <descriptionId value="841002" />
                <descriptionDisplay value="Congenital absence of skull bone" />
            </extesion>
        </snomedCT>
    </coding>
    <text value="Congenital absence of skull bone" />
</specialty>
```

---