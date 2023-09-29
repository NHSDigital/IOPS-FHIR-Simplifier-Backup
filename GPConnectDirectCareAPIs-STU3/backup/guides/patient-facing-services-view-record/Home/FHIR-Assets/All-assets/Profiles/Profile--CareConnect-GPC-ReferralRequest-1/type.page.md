## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle optional" title="Optional"></span> Optional


<h5><ins>Guidance</ins></h5>

A use-case for the `type` element has not been defined for GP Connect; however, it is expected that  `reasonCode` element can be used to represent a referral code using SNOMED CT.

<h5><ins>Example</ins></h5>

```xml
<type>
    <coding>
        <system value="http://snomed.info/sct" />
        <code value="397721007" />
        <display value="Referral by Accident and Emergency (procedure)" />
        <snomedCT>
            <url value="https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-coding-sctdescid" />
            <extension>
            <valueId value="397721007" />
                <descriptionId value="397721007" />
                <descriptionDisplay value="Referral by Accident and Emergency (procedure)" />
            </extesion>
        </snomedCT>
    </coding>
    <text value="Referral by Accident and Emergency (procedure)" />
</type>
```

---