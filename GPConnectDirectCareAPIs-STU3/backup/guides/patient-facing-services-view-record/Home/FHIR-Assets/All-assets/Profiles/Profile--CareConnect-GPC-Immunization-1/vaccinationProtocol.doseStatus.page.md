## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle mandatory" title="Mandatory"></span> Mandatory

<h5><ins>Guidance</ins></h5>

This element has a fixed value of `count` from the [Vaccination Protocol Dose Status value set](http://hl7.org/fhir/stu3/valueset-vaccination-protocol-dose-status.html)

```xml
<vaccinationProtocol>
    <doseStatus>
        <coding>
            <system value="http://hl7.org/fhir/vaccination-protocol-dose-status" />
            <code value="count" />
            <display value="Counts" />
        </coding>
    </doseStatus>
</vaccinationProtocol>
```

---