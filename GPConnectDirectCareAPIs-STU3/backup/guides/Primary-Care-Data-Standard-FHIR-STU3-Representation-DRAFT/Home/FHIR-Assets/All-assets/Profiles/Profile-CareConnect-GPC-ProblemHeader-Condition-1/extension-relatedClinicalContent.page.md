## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle required" title="Required"></span> Required


<h5><ins>Guidance</ins></h5>

The element can be used to reference clinical items and/or consultations that a user in the sending clinical system has chosen to link to this Problem.

When populating this field the provider system **MUST** include every clinical item in the patient record that provides information about the problem. This includes:

- clinical items that are directly linked to the problem in the provider system; and
- clinical items that are within a consultation topic that is linked to the problem


When populating this field the provider system must include every consultation where the problem was discussed or information about the problem was recorded. This includes:

- consultations that are directly linked to the problem in the provider system; and
- consultations that created/updated a clinical item that has been linked to the problem

<h5><ins>Example</ins></h5>

```xml
<extension>
    <url value="https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-RelatedClinicalContent-1" />
    <valueReference value="encounter-009ft54" />
</extension>
```

---