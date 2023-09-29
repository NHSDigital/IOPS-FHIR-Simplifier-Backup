## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle required" title="Required"></span> Required


<h5><ins>Guidance</ins></h5>

The `reasonCode` element can be populated with the source system’s main coded entry for the referral.

Additional, coded or text entries which are clearly captured as reasons for referral may also be included.

<h5><ins>Example</ins></h5>


```xml
<specialty>
    <coding>
        <system value="http://snomed.info/sct" />
        <code value="710952002" />
        <display value="Advocating for breastfeeding (procedure)" />
        <snomedCT>
            <url value="https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-coding-sctdescid" />
            <extension>
            <valueId value="710952002" />
                <descriptionId value="710952002" />
                <descriptionDisplay value="Advocating for breastfeeding (procedure)" />
            </extesion>
        </snomedCT>
    </coding>
    <text value="Advocating for breastfeeding (procedure)" />
</specialty>
```

---