## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle mandatory" title="Mandatory"></span> Mandatory


<h5><ins>Guidance</ins></h5>

The `subject` element will contain a reference to the Patient that the `ProcedureRequest` is regarding. This can either be as a reference within the payload, or using the `reference.identifier`.

<h5><ins>Example</ins></h5>

```xml
<subject>
    <extension>
        <url value="https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-NHSNumberVerificationStatus-1" />
        <valueCodeableConcept>
            <coding>
                <system value="https://fhir.hl7.org.uk/STU3/CodeSystem/CareConnect-NHSNumberVerificationStatus-1" />
                <code value="01" />
                <display value="Number present and verified" />
            </coding>
            <!-- text optional as already stipulated within the codeable concept -->
            <text value="Number present and verified" />
        </valueCodeableConcept>
    </extension>
    <system value="https://fhir.nhs.uk/Id/nhs-number" />
    <value value="4857773456" />
</subject>
```

---