## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle optional" title="Optional"></span> Optional


<h5><ins>Guidance</ins></h5>

The `extension.medicationTradeStatement` does not need to be populated.

This details the medication trade family or brand taken from the [CareConnect Medication Trade Family ValueSet](https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-MedicationTradeFamily). 

An extension used to identify a Trade Family or brand associated with a Medication, in particular a Virtual Therapeutic Moiety (VTM).

<h5><ins>Example</ins></h5>

```xml
<extension>
    <url value="https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-MedicationTradeFamily" />
    <valueCodeableConcept>
        <system value="https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-MedicationTradeFamily" />
                    <coding>
                <system value="http://snomed.info/sct" />
                <code value="999000641000001107" />
                <display value="The coded value for medication trade family or brand" />
            </coding>
            <text value="Free text field to be used if no code is available" />
    </valueCodeableConcept>
</extension>
```

---