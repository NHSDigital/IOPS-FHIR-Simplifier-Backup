## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle required" title="Required"></span> Required


<h5><ins>Guidance</ins></h5>

Contact details of the practitioner **MUST** be provided **IF** they are available, and the `system` element should have the [correct value](http://hl7.org/fhir/stu3/datatypes.html#contactpoint) for the information being sent.

Multiple `telecom` elements can be provided for different contact points, for example: `phone` or `email`.

In most cases, it is expected that the `use` value will be set to `work`; however, the concepts available in the value set can be found [here](http://hl7.org/fhir/stu3/valueset-contact-point-use.html).

<h5><ins>Example</ins></h5>

```xml
<telecom>
    <system value="phone" />
    <value value="1234567890" />
    <use value="work" />
</telecom>
<telecom>
    <system value="email" />
    <value value="chris.packet@example.com" />
    <use value="work" />
</telecom>
```

---
