## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle optional" title="optional"></span> Optional


<h5><ins>Guidance</ins></h5>

This element does not need to be populated.


<h5><ins>Example</ins></h5>

```xml
<extension>
    <url value="https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-EncounterTransport-1" />
    <!-- transport type -->
    <extension>
        <url value="transportType" />
        <valueCodeableConcept>
            <coding>
                <system value="http://snomed.info/sct" />
                <code value="49122002" />
                <display value="Ambulance, device (physical object)" />
            </coding>
        </valueCodeableConcept>
    </extension>
    <!-- transport period -->
    <extension>
        <url value="transportPeriod" />
        <valuePeriod>
            <start value="2022-10-28T08:06:00+00:00" />
            <end value="2022-10-28T08:14:00+00:00" />
        </valuePeriod>
    </extension>
    <!-- reason for transport -->
    <extension>
        <url value="reasonForTransport" />
        <valueString value="Integer lobortis orci ut velit bibendum consectetur." />
    </extension>
</extension>
```

---