## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle mandatory" title="Mandatory"></span> Mandatory


<h5><ins>Guidance</ins></h5>

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    A code (or set of codes) that specify this medication, or a textual description if no code is available. Usage note: This could be a standard medication code such as a code from <code>RxNorm</code>, <code>SNOMED CT</code>, <code>IDMP</code> etc. It could also be a national or local formulary code, optionally with translations to other code systems.
</div>

All medication must be represented using NHS dm+d terminology.

- The `code.coding.code` must be the NHS dm+d concept code.
- The `code.coding.display` must be the NHS dm+d concept description.


<h5><ins>Example</ins></h5>

```xml
<code>
    <coding>
        <system value="https://dmd.nhs.uk" />
        <code value="36126411000001107" />
        <display value="Morphine 10mg modified-release capsules" />
    </coding>
</code>
```

---