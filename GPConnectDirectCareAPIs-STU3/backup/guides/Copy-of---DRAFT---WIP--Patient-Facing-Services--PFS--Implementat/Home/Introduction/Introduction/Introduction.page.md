## {{page-title}}

GPIT Futures programme main vision is to accelerate and extend data access to patients in an efficient way. Part of that accelerating work is the patient facing services (PFS) which would enable seamless access of data for patients from Foundation System (FS) suppliers.

The overall design of PFS is based on Access Structured Record (ASR) API, implemented by existing and NME Foundation System suppliers. Access to the new consumer PFS APIs would be managed through NHSD API-Management APIGEE gateway.

<br/>

## Access Record: Structured | Patient Facing Services

The Access Record Structured Patient Facing Services (PFS) View Record capability enables PFS App suppliers to request and consume a patient’s GP record in a structured and coded format that is machine readable. The data will be returned as per patient’s GP record access levels set by their GP practice in their clinical system. 

The data will be made available via a standard API. Structured data allows the PFS Apps to import and process the patient data in whatever way it requires to best support the patients viewing their data on the PFS Apps.

Additional undertaking is made by GP Connect clinicians and technical modellers to advise on what is safe and useful to display for patients/citizens viewing. This includes a breakdown of the relevant FHIR profiles and examination of each element with a safety rating and recommendation. More can be found on the {{pagelink:Home/FHIR-Assets/PFS-Profiles.page.md}} section.

<br/>

## Scope

The Access Record Structured capability will expose data for a number of clinical areas. Currently supported medical record data items are: 

- <b>Allergies</b> - are observations, they contain medical record data item properties.
- <b>Medications</b> - contains data about drugs prescribed to the patient. 
- <b>Immunisations</b> - are observations, they contain medical record data item properties.
- <b>Consultations</b> - are patient’s interactions with the practice. A consultation may have a list of observations that were recorded during the consultation.
- <b>Problems</b> - contains data about medical problem. 
- <b>Investigations</b> - are a test results. Investigations can be (e.g. height or weight) or a composite (e.g. full blood count).
- <b>Outbound Referrals</b> - are typically defined as a request for transfer of care or request to provide assessment, treatment or clinical advice on the care of a patient.
- <b>Documents</b> - are electronic records that provides evidence of medical care.
- <b>Uncategorised data</b> - is not a clinical area in its own right, it represents the remainder of the clinical record which is not covered by the other clinical areas. It should not be used as a clinical area in itself. It covers several clinical concepts such as procedures, family history, measurements and many more. They are not fully standardised as clinical areas in the source system.

<div class="alert alert-warning nhsd-t-body" role="alert">
<i class="fa fa-exclamation-triangle"></i> <b>Important:</b> - The following profiles are not to be made avialble to Consumers:

- <b>Diary entries are <u>not</u></b> considered clinically safe to share with patients/citizens via PFS. Diary entries imply that a clinical action ought to be taken in the future, it does not mean it will be or has been. Additionally, if they get marked as complete, it does not necessarily mean that the action was taken. It means that the need to do the item gets ticked off (not that it was done). The ambiguity around diary entries is considered a high risk and should not be shown via PFS.​

- <b><u>Draft</u></b> consultations are <u>not</u> considered clinically safe to share with patients / citizens via PFS. They are intended just as drafts, not all of the information captured is ready to be shared. This stays in the GP system and should not be outputted to the API endpoints.</p>

- <b><u>Unfiled test results</u></b> are <u>not</u> considered clinically safe to share with patients/citizens via PFS. Only filed test results should be returned, not all of the information captured is ready to be shared. This stays in the GP system and should not be outputted to the API endpoints.</p>
</div>

<br/>

## Example scenarios 

- A patient with multiple long-term conditions views their repeat medications list to be up to date about all the medications they take. They want to view their test results for their condition(s) as they undergo regular tests. 
- Patients who have had multiple hospital admissions would like to view their documents and letters. 
- Senior citizens want to view what was discussed in their consultation as they want to refer to what was discussed.

---
