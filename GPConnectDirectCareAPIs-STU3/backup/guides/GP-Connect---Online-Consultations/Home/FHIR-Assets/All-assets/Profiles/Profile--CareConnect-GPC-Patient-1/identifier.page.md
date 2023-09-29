## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle mandatory" title="Mandatory"></span> Mandatory


<h5><ins>Guidance</ins></h5>

The `identifier` element **MUST** be populated using the [Extension-CareConnect-NHSNumberVerification](https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-NHSNumberVerificationStatus-1) element.


<h5><ins>Example</ins></h5>

```xml
<identifier>
    <extension url="https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-NHSNumberVerificationStatus-1">
        <valueCodeableConcept>
            <coding>
                <system value="https://fhir.hl7.org.uk/STU3/CodeSystem/CareConnect-NHSNumberVerificationStatus-1"/>
                <code value="01"/>
                <display value="Number present and verified"/>
            </coding>
        </valueCodeableConcept>
    </extension>
    <system value="https://fhir.nhs.uk/Id/nhs-number"/>
    <value value="4857773456"/>
</identifier>
```

---