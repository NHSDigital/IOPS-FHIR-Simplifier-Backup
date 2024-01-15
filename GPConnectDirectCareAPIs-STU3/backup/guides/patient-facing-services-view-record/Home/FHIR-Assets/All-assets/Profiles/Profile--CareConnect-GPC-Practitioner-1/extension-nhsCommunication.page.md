## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle required" title="Required"></span> Required

<h5><ins>Guidance</ins></h5>

Where available the element should be populated with the pracititioner's language information.

<h5><ins>Example</ins></h5>

```xml
<extension url="https://fhir.nhs.uk/STU3/StructureDefinition/Extension-CareConnect-GPC-NHSCommunication-1">
  <extension url="language">
    <valueCodeableConcept>
      <coding>
        <system value="https://fhir.nhs.uk/STU3/CodeSystem/CareConnect-HumanLanguage-1" />
        <code value="en" />
        <display value="English" />
      </coding>
    </valueCodeableConcept>
  </extension>

  <extension url="preferred">
    <valueBoolean value="false" />
  </extension>

  <extension url="interpreterRequired">
    <valueBoolean value="false" />
  </extension>

  <extension url="modeOfCommunication">
    <valueCodeableConcept>
      <coding>
        <system value="https://fhir.nhs.uk/STU3/CodeSystem/CareConnect-LanguageAbilityProficiency-1" />
        <code value="E" />
        <display value="Excellent" />
      </coding>
    </valueCodeableConcept>
  </extension>
</extension>
```

---