## {{page-title}}


<h5><ins>Usage</ins></h5>

<span class="mro-circle mandatory" title="Mandatory"></span> Mandatory


<h5><ins>Guidance</ins></h5>

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <b>Note</b>: This value is mandatory in the base FHIR resource so cannot be removed. It is not a concept in GP systems and as such meaning <b>MUST NOT</b> be attributed to this field in consuming systems.
</div>

The `verificationStatus` **MUST** contain a fixed value of `unconfirmed`.


<h5><ins>Example</ins></h5>

```xml
<verificationStatus value="unconfirmed" />
```

---