## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle mandatory" title="Mandatory"></span> Mandatory


<h5><ins>Guidance</ins></h5>

A reference to the patient who the medication or medical device is for - that is, to whom it will be administered.

<i class="fa fa-link" aria-hidden="true"></i> {{pagelink:Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-GPC-Patient-1}}

<h5><ins>Example</ins></h5>

```xml
 <subject>
    <identifier>
      <extension url="https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-NHSNumberVerificationStatus-1">
        <valueCodeableConcept>
          <coding>
            <system value="https://fhir.hl7.org.uk/STU3/CodeSystem/CareConnect-NHSNumberVerificationStatus-1" />
            <code value="01" />
            <display value="Number present and verified" />
          </coding>
          <text value="Number present and verified" />
        </valueCodeableConcept>
      </extension>
      <system value="https://fhir.nhs.uk/Id/nhs-number" />
      <value value="9989453456" />
    </identifier>
  </subject>
```

---