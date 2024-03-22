## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle optional" title="Optional"></span> Optional

<h5><ins>Guidance</ins></h5>

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <b>Note</b>: This value is mandatory in the base FHIR resource so cannot be removed. It is not a concept in GP systems and as such meaning <b>MUST NOT</b> be attributed to this field in consuming systems.
</div>

The `type` **MUST** be set to `allergy` for reactions which are allergenic in nature (immunological), a value of `intolerance` **MAY** be used to indicate adverse reactions (not immunologic in nature). 

Where the type is unknown the type element may be omitted.

<h5><ins>Example</ins></h5>

```xml
<type value="intolerance" />
```

---