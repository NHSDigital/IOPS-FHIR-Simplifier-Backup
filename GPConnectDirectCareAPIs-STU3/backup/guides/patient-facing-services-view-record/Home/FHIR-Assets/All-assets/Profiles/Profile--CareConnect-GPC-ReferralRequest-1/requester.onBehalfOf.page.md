## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle required" title="Required"></span> Required


<h5><ins>Guidance</ins></h5>

The `requester.onBehalfOf` element could be used when:

- that the `requester.onBehalfOf` is a practitioner
- the Organization associated with the referenced Practitioner is not the GP practice responsible for the referral

It is not expected that this element would be populated when the `requester.agent` is not a practitioner.

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