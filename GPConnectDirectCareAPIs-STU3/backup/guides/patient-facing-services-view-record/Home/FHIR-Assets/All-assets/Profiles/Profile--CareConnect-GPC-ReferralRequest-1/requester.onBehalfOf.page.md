## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle required" title="Required"></span> Required

<h5><ins>Guidance</ins></h5>

This **MUST** be populated if the `requester.agent` is a practitioner and the `Organization` associated with the referenced `Practitioner` is not the GP practice responsible for the referral. This element **SHOULD** be absent if the `requester.agent` is not a practitioner. This element **MAY** be populated or absent where the GP practice responsible for the referral is the same organisation as associated with `requester.agent` practitioner via the practitioner role.

<h5><ins>Example</ins></h5>


```xml
<requester>
    <onBehalfOf>
        <identifier>
            <system value="https://fhir.hl7.org.uk/Id/gmc-number" />
            <value value="012340000" />
            <display value="Test Practitioner" />
        </identifier>
    </onBehalfOf>
</requester>
```
---