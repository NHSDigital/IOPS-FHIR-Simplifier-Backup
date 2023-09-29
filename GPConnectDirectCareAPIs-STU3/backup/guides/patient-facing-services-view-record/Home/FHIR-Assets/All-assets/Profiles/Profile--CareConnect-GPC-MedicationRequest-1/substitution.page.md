## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle optional" title="Optional"></span> Optional

<h5><ins>Guidance</ins></h5>

Within UK healthcare, substitution is not the norm so the international FHIR definition where "If nothing is specified substitution may be done." does not align with UK healthcare prescribing best practice.

It could be unwise to assume all UK implementations will prevent substitution if not explicitly stated, especially if the same clinical system has been previously implemented outside the UK.

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <b>Note</b>: It is therefore recommended that this element is <strong>business required</strong> with a default <code>boolean</code> value of <code>false</code> to denote substitution is <strong>not allowed</strong>.
</div>

<h5><ins>Example</ins></h5>

```xml
<substitution>
    <allowed value="false" />
</substitution>
```

---