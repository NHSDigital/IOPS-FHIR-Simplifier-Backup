## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle required" title="Required"></span> Required


<h5><ins>Guidance</ins></h5>

A coded reason for the current state of the medication request.

Should only be populated when the status is `on-hold`, `cancelled` or `stopped` and when the medication request `intent` is set to `plan`.


<h5><ins>Example</ins></h5>

```xml
<extension>
    <url value="https://fhir.nhs.uk/STU3/StructureDefinition/Extension-CareConnect-GPC-MedicationStatusReason-1" />
    <extension>
        <url value="statusReason" />
        <valueCodeableConcept>
            <coding value="salg" />
            <text value="Allergy" />
        </valueCodeableConcept>
    </extension>
</extension>
```

---