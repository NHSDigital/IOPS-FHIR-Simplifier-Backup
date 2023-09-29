## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle mandatory" title="Mandatory"></span> Mandatory


<h5><ins>Guidance</ins></h5>

A reference to either:

<i class="fa fa-link"></i> {{pagelink:Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-GPC-Patient-1}}

<i class="fa fa-link"></i> {{pagelink:Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-GPC-Location-1}}

<i class="fa fa-link"></i> [Device](https://www.hl7.org/fhir/stu3/device.html)

<i class="fa fa-link"></i> [Group](https://www.hl7.org/fhir/stu3/group.html)

**List(Consultation)**

- provide a reference to the patient whom the consultation is about

<h5><ins>Example</ins></h5>

```xml
<subject>
    <reference value="patient-009oap2" />
</subject>
```

---