## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle mandatory"></span> Mandatory


<h5><ins>Guidance</ins></h5>

This details the care setting in which the medication or medical device was prescribed taken from the [CareConnect Prescribing Agency ValueSet](https://fhir.nhs.uk/STU3/ValueSet/CareConnect-PrescribingAgency-1). 

Currently this field will only support two coded entries, indicating whether the medication / medical device was prescribed by the GP practice or by another organisation. If the providing organisation has more details about the type of prescribing organisation (for example, that it was a dental practice or hospital), this **MUST** be included in the `CodeableConcept.text` field.

In the future, the coded valueset will be built on to be more specific about where a medication / medical device was prescribed. For instance, if the patient was prescribed a medication by a hospital or bought a medication over the counter then this would be coded as well as in the text.

For repeat and repeat dispensed medications / medical devices, the value identifies the care setting where the medication plan (rather than any specific issue in the plan) was authorised.

<h5><ins>Example</ins></h5>

```xml
<extension>
    <url value="https://fhir.nhs.uk/STU3/StructureDefinition/Extension-CareConnect-GPC-PrescribingAgency-1" />
    <valueCodeableConcept>
        <system value="https://fhir.nhs.uk/STU3/StructureDefinition/Extension-CareConnect-GPC-PrescribingAgency-1" />
        <coding value="prescribed-at-gp-practice">
        <text value="Prescribed at GP practice" />
    </valueCodeableConcept>
</extension>
```

---