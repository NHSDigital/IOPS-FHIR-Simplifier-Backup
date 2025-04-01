## {{page-title}}

<h5><ins>Usage</ins></h5>

#### For investigations

<span class="mro-circle required" title="Required"></span> Required

#### For diary entries

<span class="mro-circle mandatory" title="Mandatory"></span> Mandatory

<h5><ins>Guidance</ins></h5>

#### For investigations

Reference to the resource for the practitioner or organization that created the ProcedureRequest.

#### For diary entries

The person or system who entered the diary entry into the original source system.

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