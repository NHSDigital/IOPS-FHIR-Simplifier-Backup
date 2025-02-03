## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle Required" title="Required"></span> Required


<h5><ins>Guidance</ins></h5>

An extension to record the Trade Family or brand associated with a Medication. 

<h5><ins>Example</ins></h5>

```xml
    <extension url="https://fhir.nhs.uk/STU3/StructureDefinition/Extension-GPConnect-MedicationTradeFamily-1">
        <valueCodeableConcept>
            <coding>
                <system value="http://snomed.info/sct" />
                <code value="9298001000001101" />
                <display value="Panadol Extra" />
            </coding>
        </valueCodeableConcept>
    </extension>
```

---