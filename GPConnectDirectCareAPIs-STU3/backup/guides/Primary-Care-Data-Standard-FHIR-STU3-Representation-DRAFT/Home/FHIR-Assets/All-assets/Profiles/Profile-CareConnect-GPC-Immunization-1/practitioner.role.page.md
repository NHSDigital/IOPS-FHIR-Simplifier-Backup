## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle required" title="Required"></span> Required


<h5><ins>Guidance</ins></h5>

The role of the referenced practitioner, if known, from the [v2 Provider Role code system](http://hl7.org/fhir/v2/0443).

- The code `EP` (Entering Provider) **MUST** be used to designate the practitioner as having recorded the vaccination (or reason not given).
- The code `AP` (Administering Provider) **MUST** be used to designate the practitioner as having administered the vaccination or intending to if the vaccine was not given.

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>Note</strong>: This <strong>MUST</strong> be absent for if the practioner role is not known.
</div>

<h5><ins>Example</ins></h5>

```xml
<practitioner>
    <role>
        <coding>
            <system value="http://hl7.org/fhir/v2/0443" />
            <code value="AP" />
            <display value="Administering Provider" />
        </coding>
    </role>
</practitioner>
```

---