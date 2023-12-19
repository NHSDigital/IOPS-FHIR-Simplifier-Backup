## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle required" title="Required"></span> Required

<h5><ins>Guidance</ins></h5>

Items that make up the Bundle.

Provider systems **MUST** return the following resources in the Bundle:
- `Patient` matching the NHS Number sent in the body of the request
- `Organization` matching the patient’s registered GP practice, referenced from `Patient.generalPractitioner`
- `Organization` matching the organisation serving the request, if different from above, referenced from `Patient.managingOrganization`
- `Practitioner` matching the patient’s usual GP, if they have one, referenced from `Patient.generalPractitioner`
- `PractitionerRole` matching the usual GP’s role
- resources holding consultations, problems, immunisations, allergies, intolerance, medications, uncategorised data, referrals, investigations, diary entries and warnings about unsupported parameters according to the rules on {{ pagelink: construct_GPConnect-StructuredRecord-Bundle-1 }}

<h5><ins>Example</ins></h5>

```xml
<entry>

</entry>
```

---