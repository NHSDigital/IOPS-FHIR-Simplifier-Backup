## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle mandatory" title="Mandatory"></span> Mandatory


<h5><ins>Guidance</ins></h5>

The NHS England Interoperability Standards (IOPS) team have not created a `MessageDefinition` for this specification. A reference value must be added in order to pass FHIR validation, thus the base message definition has been used.


<h5><ins>Example</ins></h5>

```xml
<extension>
    <url value="MessageDefinition" />
    <valueReference>
        <reference value="https://fhir.nhs.uk/MessageDefinition" />
    </valueReference>
</extension>
```

---