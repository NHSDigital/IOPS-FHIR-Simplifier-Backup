## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle required" title="Required"></span> Required

<h5><ins>Guidance</ins></h5>

`registrationDetails.preferredBranchSurgery` with a reference to a `Location` resource representing the patient’s preferred branch surgery, see {{pagelink:Home/Build/Branch-surgeries/Index.page.md}} for more details.

<h5><ins>Example</ins></h5>

```xml
<extension url="https://fhir.nhs.uk/STU3/StructureDefinition/Extension-CareConnect-GPC-RegistrationDetails-1">
  <extension url="preferredBranchSurgery">
    <valueReference>
        <reference value="Location/785b4ff5-aced-4bdf-b7ed-34f92131ce97" />
    </valueReference>
  </extension>
</extension>
```

---