## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle required" title="Required"></span> Required


<h5><ins>Guidance</ins></h5>

The procedure code describing the vaccine that was administered or the situation code for a vaccination that was intended to be administered but was not done. See the profile for the valid codes.

<h5><ins>Example</ins></h5>

```xml
<extension>
    <url value="https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-VaccinationProcedure-1" />
    <valueCodeableConcept>
        <coding>
            <system value="http://snomed.info/sct" />
            <code value="1324681000000101" />
            <display value="Administration of first dose of severe acute respiratory syndrome coronavirus 2 vaccine (procedure)" />
        </coding>
    </valueCodeableConcept>
</extension>
```

---