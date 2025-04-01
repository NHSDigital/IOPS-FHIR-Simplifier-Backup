## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle optional" title="optional"></span> Optional


<h5><ins>Guidance</ins></h5>


<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
    <b>Warning</b>: This element has been renamed to <code>conclusionCode</code> in FHIR R4.
</div>

A coded finding of the test report that is usually produced by the organisation that performed the tests.

<h5><ins>Example</ins></h5>

```xml
<codedDiagnosis>
    <coding>
        <display value="Plantar fasciitis (disorder)" />
        <code value="202882003" />
        <system value="http://snomed.info/sct" />
        <snomedCT>
            <url value="https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-coding-sctdescid" />
            <extension>
            <valueId value="202882003" />
                <descriptionId value="202882003" />
                <descriptionDisplay value="Plantar fasciitis (disorder)" />
            </extesion>
        </snomedCT>
    </coding>
    <text value="Plantar fasciitis (disorder)" />
</codedDiagnosis>
```

---