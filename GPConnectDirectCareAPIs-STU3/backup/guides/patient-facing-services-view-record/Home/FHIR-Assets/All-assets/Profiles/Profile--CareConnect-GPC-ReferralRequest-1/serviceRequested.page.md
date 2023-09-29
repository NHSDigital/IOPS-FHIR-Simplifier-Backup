## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle optional" title="Optional"></span> Optional


<h5><ins>Guidance</ins></h5>

The `serviceRequested` element can be used if the GP clinical system also holds a distinct entry for the type of service requested.

It is not expected to be populated with the source system's main code for the referral, as it is expected that this would be populated in the `reasonCode` element of this profile.

<h5><ins>Example</ins></h5>

```xml
<serviceRequested>
    <coding>
        <system value="http://snomed.info/sct" />
        <code value="394597005" />
        <display value="Histopathology" />
        <snomedCT>
            <url value="https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-coding-sctdescid" />
            <extension>
            <valueId value="394597005" />
                <descriptionId value="394597005" />
                <descriptionDisplay value="Histopathology" />
            </extesion>
        </snomedCT>
    </coding>
    <text value="Histopathology" />
</serviceRequested>
```

---