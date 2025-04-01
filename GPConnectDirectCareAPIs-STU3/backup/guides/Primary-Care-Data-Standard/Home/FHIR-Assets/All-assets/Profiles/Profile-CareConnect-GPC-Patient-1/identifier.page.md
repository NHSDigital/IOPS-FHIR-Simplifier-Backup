## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle mandatory" title="Mandatory"></span> Mandatory

<h5><ins>Guidance</ins></h5>

The `identifier` element **MUST** be populated with any relevant business identifers including, as a minium the patient's NHS number.

<h5><ins>Example</ins></h5>

```xml
<identifier>
    <system value="https://fhir.nhs.uk/Id/nhs-number" />
    <value value="9476719931" />
</identifier>
```

---