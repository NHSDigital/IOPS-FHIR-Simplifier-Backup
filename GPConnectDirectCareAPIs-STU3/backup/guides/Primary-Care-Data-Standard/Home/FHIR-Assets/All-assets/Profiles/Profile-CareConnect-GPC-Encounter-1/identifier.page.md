## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle mandatory" title="Mandatory"></span> Mandatory


<h5><ins>Guidance</ins></h5>

The `identifier` element **MUST** be populated with a globally unique and persistent identifier (that is, it doesn’t change between requests and therefore stored with the source data). This **MUST** be scoped by a provider specific namespace for the identifier.

Where consuming systems are integrating data from this resource to their local system, they **MUST** also persist this identifier at the same time.

<h5><ins>Example</ins></h5>

```xml
<identifier>
    <system value="https://foo.bar/id/encounter" />
    <value value="3468df42-4c6a-43db-b377-c5ea264c8ab3" />
</identifier>
```

---