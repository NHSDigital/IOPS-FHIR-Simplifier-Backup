## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle optional" title="Optional"></span> Optional

<h5><ins>Guidance</ins></h5>

The security label(s) applicable to the resource.

See {{pagelink:Home/Build/FHIR-resources/Resources-not-to-be-disclosed-to-a-patient.page.md}} for more details on how to populate the element.

<h5><ins>Example</ins></h5>

```xml
<meta>
    <security>
        <system value="http://hl7.org/fhir/v3/ActCode"/>
        <code value="NOPAT"/>
        <display value="no disclosure to patient, family or caregivers without attending provider's authorization"/>
    </security>
</meta>
```

---