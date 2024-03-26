## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle optional" title="optional"></span> Optional


<h5><ins>Guidance</ins></h5>

This element should be populated if known using the `CareConnect-OutcomeOfAttendance` code system.

<i class="fa fa-link"></i> [https://fhir.hl7.org.uk/STU3/CodeSystem/CareConnect-OutcomeOfAttendance-1](https://fhir.hl7.org.uk/STU3/CodeSystem/CareConnect-OutcomeOfAttendance-1)


<h5><ins>Example</ins></h5>

```xml
<extension>
    <url value="https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-OutcomeOfAttendance-1" />
    <valueCodeableConcept>
        <system value="https://fhir.hl7.org.uk/STU3/CodeSystem/CareConnect-OutcomeOfAttendance-1" />
        <code value="3" />
        <display value="Appointment to be made at a later date" />
    </valueCodeableConcept>
</extension>
```

---