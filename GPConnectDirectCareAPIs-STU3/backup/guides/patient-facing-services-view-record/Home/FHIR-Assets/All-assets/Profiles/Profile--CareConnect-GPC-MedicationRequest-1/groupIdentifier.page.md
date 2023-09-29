## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle required" title="Required"></span> Required


<h5><ins>Guidance</ins></h5>

This element **SHOULD** be populated if the medication request has been prescribed via the Electronic Prescription Service (EPS).

If the EPS identifier is present then the identifier.value is where the EPS ID **SHOULD** also be added. The `codeSystem` for this identifier is:

<i class="fa fa-link" aria-hidden="true"></i> https://fhir.nhs.uk/Id/prescription-order-item-number


<h5><ins>Example</ins></h5>

```xml
<groupIdentifier>
    <system value="https://fhir.nhs.uk/Id/prescription-order-item-number" />
    <value value="9b4ecfde-124e-4e25-8606-a36385ce1ecc" />
</groupIdentifier>
```

---