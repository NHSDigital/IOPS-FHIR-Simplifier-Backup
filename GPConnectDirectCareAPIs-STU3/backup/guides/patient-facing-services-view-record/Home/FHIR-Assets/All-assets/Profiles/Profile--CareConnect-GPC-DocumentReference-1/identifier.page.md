## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle mandatory" title="Mandatory"></span> Mandatory

<h5><ins>Guidance</ins></h5>

This **MUST** be populated with a globally unique and persistent identifier (that is, it doesn’t change between requests and therefore stored with the source data). This **MUST** be scoped by a provider specific namespace for the identifier.

Where _consuming_ systems are integrating data from this resource to their local system, they **MUST** also persist this identifier at the same time.

<h5><ins>Example</ins></h5>

```xml
<identifier>
    <system value="https://provider.nhs.uk/data-identifier"/>
    <value value="bb2374e2-dde2-11e9-9d36-2a2ae2dbcce4"/>
</identifier>
```

---