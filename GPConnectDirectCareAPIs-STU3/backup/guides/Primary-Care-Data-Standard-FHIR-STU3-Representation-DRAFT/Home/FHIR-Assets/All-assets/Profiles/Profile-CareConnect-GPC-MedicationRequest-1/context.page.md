## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle required" title="Required"></span> Required


<h5><ins>Guidance</ins></h5>

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <b>Note</b>: This element has been removed from the FHIR R4 standard.
</div>

The consultation when the medication/medical device was authorised.

- For a `MedicationRequest` with an `intent` = `plan` this is the consultation where the plan was authorised.
- For a `MedicationRequest` with an `intent` = `order` this is the consultation where the specific issue was authorised

<h5><ins>Example</ins></h5>

```xml
<context>
    <identifier>
        <system value="https://hospital.example/visit-number" />
        <value value="visit-00425123" />
    </identifier>
</context>
```

---