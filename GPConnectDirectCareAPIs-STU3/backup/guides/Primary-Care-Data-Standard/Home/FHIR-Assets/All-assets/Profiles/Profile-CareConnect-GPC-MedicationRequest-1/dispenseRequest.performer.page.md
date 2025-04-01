## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle required" title="Required"></span> Required

<h5><ins>Guidance</ins></h5>

The organisation that dispensed the issue. This element can only be completed where the provider organisation knows explicitly which organisation dispensed the issue. 

- It cannot be assumed to be the nominated pharmacy or appliance supplier
- Only populate for a medication request with an `intent` which has the value of `order`
- This field should not be populated when a medication request has `intent` with the value of `plan`

<h5><ins>Example</ins></h5>

```xml
<dispenseRequest>
    ...
    <performer>
        <identifier>
            <system value="https://fhir.nhs.uk/Id/ods-organization-code" />
            <value value="RFR" />
        </identifier>
    </performer>
    ...
</dispenseRequest>
```

---