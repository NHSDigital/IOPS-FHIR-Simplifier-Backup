## {{page-title}}

Introduction to Outbound Referrals

### What is an Outbound Referral?
==ok to call this outbound referrals?==

A referral is typically defined as a request for transfer of care or request to provide assessment, treatment or clinical advice on the care of a patient.

A referral may be considered as a detailed document containing: 
- Relevant medical history
- Presenting needs
- Problem management to date
- Current medications
- Allergies and so on.

This profile may reference some clinical information, for example via a linked problem or consultation, but consumers should be aware that it may be necessary to access other parts of the clinical record to obtain the full clinical context.

Inbound referrals are to be returned as uncategorised data, please refer to the uncategorised data ==guide?== for further information.

#### What is an Outbound Referral with relation to GP Connect?

This GP Connect profile represents a list of outbound referral events as recorded in the GP clinical system’s referral feature or categorised area. This GP Connect profile is intended to align with the "typical" definition above, but consumers should be aware that records may be included which are outside of the scope of this definition - see Classification design decision.

The referral record represents the event of a referral being made or an intention to refer the patient (if the referral record has been recorded but the actual referral has yet to be sent). 

The referral record does not reflect the acceptance of the referral by the recipient or any onward progress of the referral.

### Referral Classification
Requirements analysis and Professional Record Standards Body (PRSB) documentation identifies a demand for a clear classification structure to the referral details, separating the reason for referral from the service referred to with each having detailed sub-classifications. GP clinical systems have taken a variety of approaches to the classification of referrals and the FHIR `ReferralRequest` has multiple elements to support the classification of referrals.

Analysis was undertaken as to whether GP clinical system data structures and recorded data, PRSB definitions and FHIR resources could be aligned and supported by SNOMED CT terminology to achieve a reliable and meaningful classification structure.
The following subsections give an overview of the analysis and conclusions reached by the curation team.
#### FHIR referral classification elements
The `ReferralRequest` resource has several elements covering the classification of the referral:
- `type`
- `serviceRequested`
- `specialty`
- `reasonCode`
- `reasonReference`

`serviceRequested`, `specialty`, `reasonCode` and `reasonReference` are fairly distinct and may support the separation of the service referred to (`serviceRequested` and `specialty`) from reason for referral (`reasonCode` and `reasonReference`). The FHIR elements may also support the sub-classification of service referred to and reason for referral. However, the full extent to which the sub-classification could be achieved was not fully investigated for the reason described in the following sections.
#### GP clinical systems
There is limited commonality across GP clinical systems as to the meta data associated with their referral classification.

All GP clinical systems have a READ/SNOMED CT coded field as the main code for the referral. This may be constrained to a referral procedure code hierarchy (`descendants of 3457005 | Patient referral (procedure) |`) or open to a much wider selection of codes which can extend beyond the recognised definition of a referral. GP clinical systems that constrain to the referral procedure codes (for a new referral entry) may contain other codes due to GP2GP transfers or legacy data.

Analysis of a large referral record set across two GP systems providers identified the following common examples for the main coded classification of the referral:
- Orthopaedic referral
- ENT referral
- Refer to physiotherapist
- Referral to musculoskeletal clinic
- Referral for further care
- Dermatological referral
- Refer for ultrasound investigation
- Referral to community mental health team
- Advice and guidance request sent
- Fast track referral for suspected skin cancer
- 2 week rule referral - upper GI

The main referral code can therefore be either a reason for referral or referred to service and thus does not align distinctly to any of the FHIR elements.

The GP system may have additional non-READ/SNOMED CT coded classification fields with fixed or locally configured valuesets. These are often optional fields. These fields may have valuesets which align to or span reason for referral and referred to service.

#### Referrals and SNOMED CT
The SNOMED CT “is a” hierarchy (`3457005 | Patient referral (procedure) |`) was considered as a potential valueset for referrals. It includes pre-coordinated referral concepts of various patterns which span all the classification elements listed above:

- Referral to institution (for example, hospital)
- Referral to speciality (for example, department)
- Referral to specialist (for example, professional)
- Referral to administrative service (for example, diabetic register)
- Referral for procedures
- Referral for findings/disorders
- Referral statuses (for example, referral accepted by, referral cancelled by)

However, whilst terms span the desired classifications, an acceptable structure to separate the terms into the desired classifications was not found. While these concepts could be formally modelled within SNOMED and classified using description logic, such attributes do not yet exist, and the concepts are ‘primitive’ with minimal (and often approximate) manually assigned is a relationships.

SNOMED content in this area will not support retrieval behaviour, for example:

- `183523005 | Referral to gastroenterology service (procedure) |` and `306308009 | Referral to gastrointestinal surgeon (procedure) |` are unrelated
- `892201000000106 | Fast track referral for suspected lower gastrointestinal cancer` and `276401000000108 | Fast track referral for suspected colorectal cancer (procedure) |` are siblings rather than the former subsuming the latter Neither does SNOMED support the inference that ‘Fast track referral for suspected lower gastrointestinal cancer’ is a ‘Referral to gastroenterology service’.
The terminology in its current form is therefore unlikely to support the structured classification (as it crosses over such classification) and is not suited to structured retrieval queries.

####Classification design decision
The analysis provided no clear structure to apply to classification of referrals which the current data in GP clinical systems can support. The referrals SNOMED terminology does not lend itself to give benefit to a structured classification. The main coded classification of a referral in GP clinical systems does not clearly align to any element of the `referralRequest`.

It does not seem practical to enforce a structure to the existing data for referral classification. The `reasonCode` has been selected for populating with the main coding of the referral because it:

- is a codeableConcept
- supports multiple values
- is more suited to a wide valueset than alternative elements
Providers **MUST** therefore return their main READ/SNOMED CT code for the referral in the `reasonCode`. Additionally, providers **MUST** return all other referral classification detail. Providers **MAY** populate additional detail to the `serviceRequested`, `specialty`, `reasonCode` (in addition to the main referral code), `supportingInfo` and/or `note` element(s) as appropriate to the nature of its data.

Consumer systems should be aware that, as a consequence of not constraining the allowable codes, some provider responses may include amongst their coded entries for referrals some codes which may be a reason for referral or do not relate to a transfer of care such as

- Abdominal pain
- Chest pain
- Full blood count (FBC)
- Thyroid Function Test

### Referrals via the NHS e-Referral Service
Referrals made via the NHS e-Referral Service (eRS) **MUST** be included by the provider where they are recorded in the GP clinical system. The Unique Booking Reference Number (UBRN) **MUST** be included as an `identifier` if it is captured against the referral record.

Consumers should be aware that referral details may be limited for referrals via eRS or may be more likely to vary from the resulting referral. Examples of limited details:

- `recipient` is not specified
- `reasonCode` is non-specific - for example, ‘Referral for further care’
The examples above also represent general data quality issues and can apply to any referral not just those via eRS.

### Referrer details
The provider **MUST** populate the `requester` with the practitioner who recorded the referral, if available. This may be a clinician or a member of the administrative staff. The role, organisation and contact details for the referrer **MUST** be included with the bundled resource as available.

If the organisation referenced from the bundled `practitioner` resource is not the GP practice responsible for the referral, then the `onBehalfOf` element **SHOULD** reference to an `organization` resource for the GP practice responsible for the referral.

### Referral status
GP clinical systems support recording the status for a referral or derive a status according to the actions which have been taken for the referral. However, the statuses are not standardised across GP clinical systems. It is also understood that the GP practice may only be aware of a status change retrospectively and that the status of referrals are not routinely maintained in many GP practices.

Providers **MUST** set the `status` of the referral as `unknown` for all referrals.

Consumers **MUST NOT** portray any referrals as indicating current involvement by recipients or any other interpretation of the status of the referral.

Where details of the progress or outcome of the referral are captured in the GP clinical system in a structured form they **SHOULD** be populated in the `note` element as appropriate key value pairs.

### Referral priority
This is the priority given by the GP practice for the referral. This may differ from the priority given to the referral by the recipient.

The `priority` is a restricted valueset mapped to the eRS priority codes. The source GP clinical system may support priority values other than the eRS priority codes. If the priority in the source system is not one of the eRS priority codes and cannot be mapped to an eRS priority code, then a priority MUST NOT be included and the source system `priority` **MUST** be included as a key value pair in the `note` element.

### Date of referral
All GP clinical systems have a user selection date field against a referral. Providers **MUST** populate the `authoredOn` element with the user entered referral date.

Consumers should be aware that the date may have slightly different meaning according to the GP clinical system and local practice for recording referrals.

### Using the List resource for referral queries
The result of a query for referral details **MUST** return a `List` containing references to all `ReferralRequest` resources that are returned.

The `List` **MUST** be populated in line with the guidance on `List` resources.

If the `List` is empty, then an empty `List` **MUST** be returned with an `emptyReason` with the value `no-content-recorded`.

## Quick links

* [Elements of the `ReferralRequest` profile and how to populate and consume them](https://developer.nhs.uk/apis/gpconnect-1-5-0/accessrecord_structured_development_referralrequest.html)
* [FHIR&reg; ReferralRequest example](https://developer.nhs.uk/apis/gpconnect-1-5-0/accessrecord_structured_development_fhir_examples_referrals.html)

==add hazard log & test data?==

