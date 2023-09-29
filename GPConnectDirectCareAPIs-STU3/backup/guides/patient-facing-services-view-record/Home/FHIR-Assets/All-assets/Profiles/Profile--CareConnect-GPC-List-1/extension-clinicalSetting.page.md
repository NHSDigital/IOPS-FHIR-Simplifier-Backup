## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle required" title="Required"></span> Required


<h5><ins>Guidance</ins></h5>

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <b>Note</b>: This element has been renamed to <code>careSettingType</code> in FHIR UK Core.
</div>

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
    <b>Warning</b>: The <a href="https://termbrowser.nhs.uk/?perspective=full&conceptId1=999000381000000107">SNOMED value-set</a> which this element recommends is inactive.
</div>

This element should be populated with the care setting that the activity relates to, providing it is known by the provider system. It is recommended to use a value from the `UKCore-List.extension:careSettingType` value-set when populating this element.


<i class="fa fa-link"></i> [Value-set: UK Core Care Setting Type](https://simplifier.net/hl7fhirukcorer4/ukcore-caresettingtype)

<h5><ins>Example</ins></h5>

```xml
<extension>
    <url value="https://fhir.nhs.uk/STU3/StructureDefinition/Extension-CareConnect-GPC-ClinicalSetting-1" />
    <valueCodeableConcept>
        <coding>
            <system value="http://snomed.info/sct" />
            <code value="788007007" />
            <display value="General practice service" />
        </coding>
    </valueCodeableConcept>
</extension>
```

---