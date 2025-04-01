## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle optional" title="Optional"></span> Optional


<h5><ins>Guidance</ins></h5>

A use-case for the `priority` element has not been defined for use in GP Connect.

<h5><ins>Example</ins></h5>

```xml
<priority>
    <coding>
        <system value="http://hl7.org/fhir/v3/ActPriority" />
        <code value="EL" />
        <display value="Beneficial to the patient but not essential for survival." />
    </coding>
    <text>Beneficial to the patient but not essential for survival.</text>
</priority>
```

---