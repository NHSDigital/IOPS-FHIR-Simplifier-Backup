## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle optional" title="Optional"></span> Optional


<h5><ins>Guidance</ins></h5>

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
    <b>Warning</b>: This element has been removed in the FHIR R4 standard.
</div>

It's expected that in most cases that this value <b>WILL NOT</b> be populated. This is due to the information not necessarily being known in the GP system.

This element would typically be populated if the value in the `taken` element is `n` (Negative assertion that patient has not taken medication).

<h5><ins>Example</ins></h5>

```xml
<reasonNotTaken>
    <system value="http://snomed.info/sct" />
    <value value="182864000" />
    <display value="Drug not taken - side-effects" />
</reasonNotTaken>
```

---