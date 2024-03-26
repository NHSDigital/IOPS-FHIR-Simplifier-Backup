## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle mandatory" title="Mandatory"></span> Mandatory


<h5><ins>Guidance</ins></h5>

This `identifier` element **MUST** be populated with a globally unique and persistent identifier (that is, it doesn’t change between requests and therefore stored with the source data). This **MUST** be scoped by a provider specific namespace for the identifier.

Where consuming systems are integrating data from this resource to their local system, they MUST also persist this identifier at the same time.

If the EPS identifier is present then the identifier.value is where the EPS ID **SHOULD** also be added. The `codeSystem` for this identifier is:

<i class="fa fa-link" aria-hidden="true"></i> https://fhir.nhs.uk/Id/prescription-order-item-number

<h5><ins>Example</ins></h5>

```xml
<identifier>
    <system value="https://fhir.nhs.uk/Id/prescription-order-item-number" />
    <value value="9b4ecfde-124e-4e25-8606-a36385ce1ecc" />
</identifier>
```

---