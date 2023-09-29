## {{page-title}}

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
<b>Summary</b>: Introduction to the Access Record Structured PFS capability
</div>

### Purpose
The Access Record Structured PFS capability enables an NHS system to request and consume a patient’s GP record in a structured and coded format that is machine readable. The data will be made available via a standard API. Structured data allows the consuming system to import and process the patient data in whatever way it requires to best support patients and the healthcare professionals treating them. GP Connect does not place any specific restrictions on how the data is processed so long as the data is only used for the direct care of the patient and the system meets the specified GP Connect consumer requirements (including information governance and clinical safety standards).

### Scope
The Access Record Structured PFS capability will expose data for a number of clinical areas. This release supports:

1. Medications
2. Allergies
3. Immunizations
4. Uncategorised items
5. Consultations*
6. Problems
7. Investigations
8. Referrals (Outbound)

\* Not including <b>Draft</b> Consultations 

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
<b>Note</b>: Documents are defined in a separate Access Document capability, which complements Access Record Structured by allowing the querying and retrieval of documents for a patient.
</div>

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
<b>Note</b>: Subsequent releases are to be scoped FHIR® version
</div>

<b>Roadmap</b>: Subsequent releases are to be scoped FHIR® version

### FHIR® version
Standard for Trial Use 3 (STU3) is the version of FHIR which was adopted for the Access Record Structured PFS capability. This was the current version at the time development was started by the GP systems suppliers.

The project is considering it’s approach to uplifting to UKCore (the UK specific project for FHIR based on R4). It is currently exploring the mapping between versions and is involved in a proof of concept to see if it is possible to transform between the current GP Connect profiles detailed in this specification and the new UKCore profiles. If successful this may enable consumer suppliers to develop in either version. 

---