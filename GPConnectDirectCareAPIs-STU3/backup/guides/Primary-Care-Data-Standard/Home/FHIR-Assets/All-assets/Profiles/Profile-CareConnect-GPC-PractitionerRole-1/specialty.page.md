## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle optional" title="Optional"></span> Optional

<h5><ins>Guidance</ins></h5>

Specific specialty of the practitioner

<h5><ins>Example</ins></h5>

```xml
<specialty>
    <coding>
        <system value="http://hl7.org/fhir/practitioner-specialty" />
        <code value="cardio" />
        <display value="Cardiologist" />
        <snomedCT>
            <url value="https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-coding-sctdescid" />
            <extension>
            <valueId value="cardio" />
                <descriptionId value="cardio" />
                <descriptionDisplay value="Cardiologist" />
            </extesion>
        </snomedCT>
    </coding>
    <text value="Cardiologist" />
</specialty>
```
---