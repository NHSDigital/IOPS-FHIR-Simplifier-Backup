## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle optional" title="Optional"></span> Optional


<h5><ins>Guidance</ins></h5>

The `requisition` element does not need to be populated.

<h5><ins>Example</ins></h5>

```xml
<requisition>
    <use value="official" />
    <type value="VN" />
    <system value="https://foo.bar/id/requisition" />
    <value value="42068246-fbbb-44e8-825d-91f091273263" />
    <period>
        <start value="2022-11-01T00:00:00Z" />
        <end value="2022-11-04T00:00:00Z" />
    </period>
    <assigner>
        <reference>
            <identifier>
                <system value="https://fhir.nhs.uk/Id/sds-user-id"/>
                <value value="UNK"/>
            </identifier>
        </reference>
    <assigner>
</requisition>
```

---