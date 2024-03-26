## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle optional" title="Optional"></span> Optional


<h5><ins>Guidance</ins></h5>

The `extension.changeSummary` does not need to be populated.


<h5><ins>Example</ins></h5>

```xml
<extension>
    <url value="https://fhir.nhs.uk/STU3/StructureDefinition/Extension-CareConnect-GPC-MedicationChangeSummary-1" />
    <extension>
        <id value="4095fcc9-c0ae-4f05-b5db-1fb648fe7bda" />
        <url value="https://fhir.nhs.uk/STU3/ValueSet/CareConnect-MedicationChangeStatus-1" />
        <valueCode value="Amended" />        
    </extension>
    <extension>
        <id value="4095fcc9-c0ae-4f05-b5db-1fb648fe7bda" />
        <url value="indicationForChange" />
        <valueCodeableConcept>
            <coding>
                <system value="http://snomed.info/sct" />
                <code value="294091000119104" />
                <display value="Headache caused by drug (finding)" />
            </coding>
        </valueCodeableConcept>  
    </extension>
    <extension>
        <id value="4095fcc9-c0ae-4f05-b5db-1fb648fe7bda" />
        <url value="dateChanged" />
        <valueDateTime value="2022-02-23T14:07:48+00:00" />
    </extension>
    <extension>
        <id value="4095fcc9-c0ae-4f05-b5db-1fb648fe7bda" />
        <url value="detailsOfAmendment" />
        <valueString value="Amended as patient reported side-effects of headaches" />
    </extension>
</extension>
```


---