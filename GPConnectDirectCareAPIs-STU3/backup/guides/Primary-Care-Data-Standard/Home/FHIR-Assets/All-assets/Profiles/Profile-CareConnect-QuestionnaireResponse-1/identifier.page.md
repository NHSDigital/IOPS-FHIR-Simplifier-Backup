## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle mandatory" title="Mandatory"></span> Mandatory

<h5><ins>Guidance</ins></h5>

This **MUST** be populated with a globally unique and persistent identifier (that is, it doesn’t change between requests and therefore stored with the source data). This **MUST** be scoped by a provider specific namespace for the identifier.

There may be more than one identifier where data has been migrated across practices or provider systems and different provider specific identifiers have been assigned.

Where _consuming_ systems are integrating data from this resource to their local system, they **MUST** also persist this identifier at the same time.

<h5><ins>Example</ins></h5>

```xml
<identifier>
    <system value="https://foo.bar/id/questionnaire-response" />
    <value value="fef26348-ccd1-440b-940e-ba1ec058cf21" />
</identifier>
```

---