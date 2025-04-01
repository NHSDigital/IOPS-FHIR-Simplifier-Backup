## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle required" title="Required"></span> Required

<h5><ins>Guidance</ins></h5>

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <b>Note</b>: The value set for this STU3 extension aligns with the legacy HL7v3 PrescriptionTreatmentType vocabulary.
</div>

- acute
- repeat
- repeat dispensing
- delayed prescribing.

If UK Core R4 is extended to support this type of data then the extension name should ideally not be called `prescriptionType` as it confused with a different legacy HL7v3 vocabulary for `prescriptionType` which serves a different purpose.

This element provides an explicit repeat/acute flag rather than deriving it from presence of extension elements or repeatNumber.

In exceptional cases where for legacy data there is no `prescriptionType` recorded in the system then this **MUST** not populate the element and the consumer **SHOULD** use the text `No information available`.

<h5><ins>Example</ins></h5>

```xml
<extension>
    <url value="https://fhir.nhs.uk/STU3/StructureDefinition/Extension-CareConnect-GPC-PrescriptionType-1" />
    <valueCodeableConcept>
        <system value="https://fhir.nhs.uk/STU3/CodeSystem/CareConnect-PrescriptionType-1" />
        <code value="acute" />
    </valueCodeableConcept>
</extension>
```

---