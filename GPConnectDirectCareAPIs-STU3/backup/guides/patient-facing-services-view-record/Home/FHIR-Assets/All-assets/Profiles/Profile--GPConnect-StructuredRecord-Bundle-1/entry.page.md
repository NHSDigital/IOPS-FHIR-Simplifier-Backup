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
    <resource>
        <Patient>
        <id value='04603d77-1a4e-4d63-b246-d7504f8bd833'/>
        <meta>
            <versionId value='1469448000000'/>
            <profile value='https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Patient-1'/>
        </meta>
        <extension url='https://fhir.nhs.uk/STU3/StructureDefinition/Extension-CareConnect-GPC-RegistrationDetails-1'>
            <extension url='registrationPeriod'>
            <valuePeriod>
                <start value='1962-07-13T00:00:00+00:00'/>
            </valuePeriod>
            </extension>
        </extension>
        <identifier>
            <extension url='https://fhir.nhs.uk/STU3/StructureDefinition/Extension-CareConnect-GPC-NHSNumberVerificationStatus-1'>
            <valueCodeableConcept>
                <coding>
                <system value='https://fhir.nhs.uk/CareConnect-NHSNumberVerificationStatus-1'/>
                <code value='01'/>
                <display value='Number present and verified'/>
                </coding>
            </valueCodeableConcept>
            </extension>
            <system value='https://fhir.nhs.uk/Id/nhs-number'/>
            <value value='9999999999'/>
        </identifier>
        <active value='true'/>
        <name>
            <use value='official'/>
            <text value='JACKSON Jane (Miss)'/>
            <family value='Jackson'/>
            <given value='Jane'/>
            <prefix value='Miss'/>
        </name>
        <telecom>
            <system value='phone'/>
            <value value='01454587554'/>
            <use value='home'/>
        </telecom>
        <gender value='female'/>
        <birthDate value='1952-05-31'/>
        <address>
            <use value='home'/>
            <type value='physical'/>
            <line value='Cable Place'/>
            <line value='Roundhay'/>
            <city value='Leeds'/>
            <district value='West Yorkshire'/>
            <postalCode value='LS1 5HT'/>
        </address>
        <generalPractitioner>
            <reference value='Practitioner/6c41ebfd-57c3-4162-9d7b-208c171a2fd7'/>
        </generalPractitioner>
        <managingOrganization>
            <reference value='Organization/db67f447-b30d-442a-8e31-6918d1367eeb'/>
        </managingOrganization>
        </Patient>
    </resource>
</entry>
```

---