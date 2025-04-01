## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle required" title="Required"></span> Required

<h5><ins>Guidance</ins></h5>

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <b>Note</b>: The encounter is part of the base resource in FHIR R4 / UK CORE.
</div>

Providing it is known, the `extension.encounter` should be populated with a reference to the consultation where the allergy was first recorded.

<h5><ins>Example</ins></h5>

```xml
<extension>
    <url value="http://hl7.org/fhir/StructureDefinition/encounter-associatedEncounter" />
    <valueReference value="urn:uuid:85acc1ae-6b9d-4a9f-9840-60d6cac081cd" />
</extension>
```

---