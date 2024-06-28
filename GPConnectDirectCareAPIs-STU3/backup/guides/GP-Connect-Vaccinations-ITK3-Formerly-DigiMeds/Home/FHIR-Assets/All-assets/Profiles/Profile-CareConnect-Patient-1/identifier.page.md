## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle mandatory" title="Mandatory"></span> Mandatory


<h5><ins>Guidance</ins></h5>

The `identifier` element **MUST** be populated using the [Extension-CareConnect-NHSNumberVerification](https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-NHSNumberVerificationStatus-1) element.

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>Note</strong>: The <code>text</code> element has optional cardinality and does not need to be populated. The human-readable value for the NHS Number Verification Status provided is articulated within the <code>display</code> value within the <code>valueCodeableConcept</code> element.
</div>

<h5><ins>Example</ins></h5>

```xml
<identifier>
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
</identifier>
```

---