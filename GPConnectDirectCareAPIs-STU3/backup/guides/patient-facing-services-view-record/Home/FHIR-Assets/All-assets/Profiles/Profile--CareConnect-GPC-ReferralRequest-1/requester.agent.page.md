## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle required" title="Required"></span> Required

<h5><ins>Guidance</ins></h5>

The preferred agent is the practitioner responsible for the decision to refer the patient. If the referral is not attributed to a practitioner, then any of the other resource options **MAY** be used as most appropriate. If the referral does not clearly identify responsibility for the referral decision or action, this **MUST** be the user who recorded the referral.

<h5><ins>Example</ins></h5>


```xml
<requester>
    <agent>
        <identifier>
            <system value="https://fhir.hl7.org.uk/Id/gmc-number" />
            <value value="000000000" />
            <display value="Test GP" />
        </identifier>
    </agent>
</requester>
```
---