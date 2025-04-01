## {{page-title}}

<h5><ins>Usage</ins></h5>

#### For investigations

<span class="mro-circle required" title="Required"></span> Required

#### For diary entries

<span class="mro-circle optional" title="Optional"></span> Optional

<h5><ins>Guidance</ins></h5>

#### For investigations

Reference to the resource for the practitioner or organization that is requested to perform this request the ProcedureRequest.

<h5><ins>Example</ins></h5>

```xml
<performer>
    <reference>
        <identifier>
            <system value="https://fhir.hl7.org.uk/Id/gmc-number" />
            <value value="000000000" />
            <display value="Test GP" />
        </identifier>
    </reference>
</performer>
```

#### For diary entries

A use-case for the `performer` element has not been defined.

---