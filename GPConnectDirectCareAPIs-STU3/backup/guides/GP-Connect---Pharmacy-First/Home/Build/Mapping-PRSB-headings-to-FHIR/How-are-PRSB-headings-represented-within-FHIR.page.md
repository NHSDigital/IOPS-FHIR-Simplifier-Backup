## {{page-title}}


In previous ITK3 specifications, the NHS has asked providers to send this as HTML within the `Composition.section.text` element, along with a SNOMED code within `Composition.section.code`.

GP Connect does not follow this pattern, and prefers that uncategorised data be sent within the following FHIR profiles:

- {{pagelink:Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-GPC-ClinicalImpression-1}}
- {{pagelink:Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-Flag-1}}
- {{pagelink:Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-GPC-Observation-1}}


A value from the following code system should be used within `meta.tag` to articulate which headings the data item being represented aligns to. A link to the code system can be found below.

{{pagelink:Home/FHIR-Assets/All-assets/Code-systems/Code-system--RecordStandardHeadings}}

In the event of multiple values for the same heading being sent, additional profiles will be sent.

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <b>Note</b>: Only the main headings within PRSB standards are represented within this code-system. Sub-headings are not to be used, and can instead be inferred by the data being expressed in the profile.
</div>

More information about this can be found within the {{pagelink:Home/Build/Tagging-payloads-with-meta.tag}} section of this specification.

---