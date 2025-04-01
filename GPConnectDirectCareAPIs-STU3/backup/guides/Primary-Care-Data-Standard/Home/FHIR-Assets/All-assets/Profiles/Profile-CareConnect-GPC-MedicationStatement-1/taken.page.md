## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle mandatory" title="Mandatory"></span> Mandatory


<h5><ins>Guidance</ins></h5>

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
    <b>Warning</b>: This element has been removed in the FHIR R4 standard.
</div>

A mandatory element that needs to be supplied due to the cardinality if using STU3 / CareConnect.

It is expected that, in most cases, the administration of medication cannot be confirmed and will be the following code: `unk` (Unknown) from the [MedicationStatementTaken ValueSet](http://hl7.org/fhir/stu3/valueset-medication-statement-taken.html).


<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <b>Note</b>: If the administration of medication is known, then it <b>SHOULD</b> be provided.
</div>


<h5><ins>Example</ins></h5>

```xml
<taken value="unk" />
```

---