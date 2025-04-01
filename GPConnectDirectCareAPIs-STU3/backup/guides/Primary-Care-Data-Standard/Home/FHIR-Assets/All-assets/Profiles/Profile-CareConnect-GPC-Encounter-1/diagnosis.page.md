## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle optional" title="Optional"></span> Optional

<h5><ins>Guidance</ins></h5>

This element does not need to be populated.

The diagnosis will be associated to the consultation via the `List` profile.

<h5><ins>Example</ins></h5>

```xml
<diagnosis>
    <condition>
        <reference value="condition-or-procedure--00sd12ab" />
    </condition>
    <role>
        <coding>
            <system value="http://hl7.org/fhir/ValueSet/diagnosis-role" />
            <code value="AD" />
            <display value="Admission diagnosis" />
        </coding>
    </role>
    <rank value="23" />
</diagnosis>
```

---