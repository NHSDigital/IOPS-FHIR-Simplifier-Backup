## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle optional" title="Optional"></span> Optional


<h5><ins>Guidance</ins></h5>


The `identifier` **MUST** be populated with a globally unique and persistent identifier (that is, it doesn’t change between requests and therefore stored with the source data). This **MUST** be scoped by a provider specific namespace for the identifier.

Where consuming systems are integrating data from this resource to their local system, they **MUST** also persist this identifier at the same time.

If the referral was made via the e-Referral Service and a Unique Booking Reference Number (UBRN) exists for the referral, then it **MUST** be included as an identifier. The system identifier for this is `https://fhir.nhs.uk/Id/ubr-number`.

<h5><ins>Example</ins></h5>

```xml
<identifier>
    <system value="https://foo.bar/id/referral-request" />
    <value value="fef26348-ccd1-440b-940e-ba1ec058cf21" />
</identifier>
```

---