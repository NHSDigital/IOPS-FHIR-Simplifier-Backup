## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle mandatory" title="Mandatory"></span> Mandatory

<h5><ins>Guidance</ins></h5>

### For structural lists

Reference to the `Patient` profile.

### For lists used in consultations

Reference to the `Patient` profile for the patient whose patient record contains a consultation represented by this List profile.

The patient reference is provided by all Lists in the structure rather than the top-level List(Consultation) only.

<h5><ins>Example</ins></h5>

```xml
<subject>
    <reference value="patient-009oap2" />
</subject>
```

---