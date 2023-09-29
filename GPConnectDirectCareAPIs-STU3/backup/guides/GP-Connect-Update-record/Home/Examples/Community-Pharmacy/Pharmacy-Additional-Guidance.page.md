## {{page-title}}

The guidance covers the following areas, related to pharmacy first use case:

#### Auto ingest

Specfically for Pharmacy First, auto ingest is the scenario accounted for wherby all patient information presented to the GP system and the patient record will be automatically added to the patient record without notification to the GP system or service.  Therefore, any presentation of patient information to the GP service that requires an additional action and/or followup will be dealt with through existing processes.  For example where a followup telephone call/email is required.   

#### Encounter

From a pharmacy perspective and encounter is a reference for when a citizen/patient has a dialogue with a pharmacist healthcare professional regarding their medical needs. Where the pharmacist has prescribed medication, ideally, the data items listed below are recorded on the pharmacy system and used to update the patients record on the GP system.

* Attendance
* Episode of Care
* Incoming Referral
* Reason

The pharmacy mapping shows that there are data items that exist on the GP system (Adopting the FHIR/STU3 Profile) that are not required but need to be set as required on the pharmacy system. Therefore, it is recommended that local pharmacy guidelines and/or system practices should be used to ensure data item requirements.


#### Consent


From a Pharmacy perspective: Patient consents to their patient record being updated and information can be shared with Patient Facing Services (PFS). The variance of consenting levels is shown below:


* Patient consents to their pharmacy record being updated only (Local patient information consenting only)
* Patient consents to their pharmacy record and their GP record being updated but their information cannot be shared with the Patient Facing Services (PFS) team. Therefore, their updated information does not appear on the NHS App.
* Patient consents to their information being shared across their GP record and the PFS team, to be visible on the NHS App.

These consenting options will be implemented at pharmacy level, through best practice guidelines.
This information is based on each encounter and would not supersede consenting information set at the GP practice.





#### Observations

For pharmacy, the observation refers to the time or time period where the observation is being asserted as being true.

#### Medication

Enables pharmacy to prescribe and dispense prescription only medicines, whereas contraception checking allows pharmacists to supply prescription only medications under a PGD (xxxxxxxx), they wouldn’t necessarily be a prescriber.

Discretion is required by pharmacists to ensure that the usefulness of the information sent and presented to a GP record has a purpose.  For example, a GP practice unlikely to be interested in a packet of paracetamol - though in some instances they may be. This would need to be within policy / guidance for Pharmacists and discussed/agreed across clinicians and does not affect the Update Record specification. 

**Medication - Status** - Pharmacy will need to use relevant subset of **status** as not all options will be appropriate to use for sending into record. 

**Medication Category** - The value set here needs to be looked at to give guidance to pharmacy suppliers as to what to put here.

**Medication Reference** - The description of the medication

**Extension (lastIssueDate)** - systems could prompt for if repeat prescription. Some of this work will fall under local pharmacy guidance and under the Implementation Guidance for Pharmacy.

----

## Profile Guidance - Pharmacy Specific

### Observation - blood pressure guidance

Please note there are no exception rules for recording blood pressure (BP) but the following should be taken into consuderation.  Blood pressure is one of the most common observations that is recorded in GP records.  For further technical information for how BP is represented through HL7FHIR please refer to the [HL7FHIR Information page](http://hl7.org/fhir/STU3/bp.html)

**Effective[x]:** - The time period that the observation took place

**Reference Range:** - The reference range provides a guide for the interpretation of the results

**Observation Elements:** Where there is no header/panel code and only the blood pressure systolic and diastolic components are recorded, then the following codes must be recorded:

**SNOMED codes** conceptID =**'75367002'** </br>
**Observable entity** Desciption ID = **'125176019'** (Blood Pressure)

### Medication

**Extension(lastIssueDate):** - Maybe used to record additional information

**Extension(prescribingAgency):** - it may not always be a prescription, therefore, maybe used to record additional information

**Status:** - Pharmacy will need to use a subset of this as not all appropriate to use for sending into record
**Category:** - The value set here needs to be looked at to give guidance to pharmacy suppliers as which options are expected for this item

**MedicationReference:** - For Update Record this will be a description of the medication

For further information on recording observation - blood pressure information, please refer to the [API Hub and national defined Messaging API information](https://developer.nhs.uk/apis/gpconnect-1-5-0/accessrecord_structured_development_observation_bloodPressure.html)



