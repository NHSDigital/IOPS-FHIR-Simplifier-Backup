## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle required" title="Required"></span> Required


<h5><ins>Guidance</ins></h5>

This field is used to create the links between `MedicationRequest` profiles to represent the medication ordering process as described here. 

This **MUST** be used when a profile has an intent element that is set to `order` and is `basedOn` a `MedicationRequest` profile that has an intent set to `plan`.

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
    <b>Warning</b>: DO NOT USE for authorisations - that is, for a <code>MedicationRequest</code> with intent of plan.
</div>


<h5><ins>Example</ins></h5>

```xml
<basedOn>
    <reference value="medication-request-5485984" />
</basedOn>
```

---