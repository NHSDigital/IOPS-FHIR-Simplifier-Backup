## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle required" title="Required"></span> Required


<h5><ins>Guidance</ins></h5>

This element should normally be used to link to a `MedicationRequest` which authorised the medication.

This element could also potentially reference all medication requests relating to the medication or relevant instances of CarePlan or ServiceRequest.

This should not be confused with `MedicationStatement.derivedFrom` which should only be used to reference information that can’t be referenced here.

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <b>Note</b>: For GP Connect, each `MedicationStatement` <b>MUST</b> be based on a <code>MedicationRequest</code> with <code>intent</code> set to <code>plan</code>.
</div>

<h5><ins>Example</ins></h5>

```xml
<basedOn>
    <reference value="medication-request-5485984" />
</basedOn>
```

---