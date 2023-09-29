## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle required" title="Required"></span> Required


<h5><ins>Guidance</ins></h5>

The `requester` element can be used to contain a reference to the resource for the practitioner or organization that initiated this `ProcedureRequest`.

<h5><ins>Example</ins></h5>

```xml
<requester>
    <reference>
        <identifier>
            <system value="https://fhir.hl7.org.uk/Id/gmc-number" />
            <value value="000000000" />
            <display value="Test GP" />
        </identifier>
    </reference>
</requester>
```

---