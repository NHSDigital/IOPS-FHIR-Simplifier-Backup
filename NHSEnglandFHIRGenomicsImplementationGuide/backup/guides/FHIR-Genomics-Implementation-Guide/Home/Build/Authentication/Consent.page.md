## {{page-title}}

## Consent for Order Management

Consent within Genomics can be split into two main categories:
* General consent to having genetic/genomic testing performed, including consent obtained from family members for cascade testing
* Consent allowing for storage and secondary use of data, e.g. for research. Most relevant to WGS test requests, allowing storage of data in the National Genomic Research Library.

### Consent for Testing

Consent for testing is assumed to have been taken when submitting a test request to the Genomic Medicine Service. As of publication, capturing of this consent information is not considered in scope for storage in the central broker, however, this information can be represented using FHIR Consent resources. Guidance on how this information should be captured if general consent is later deemed in scope for the GMS.

Currently Consent for Testing is expected to be captured as part of the Unified Genomic Record, alongside wider consent, e.g. to have family members contacted regarding testing etc.

### Consent for Research

Currently, representation of Consent for Research within the Genomic Medicine Service is limited to the [Record of Discussion form](https://github.com/NHSDigital/NHSDigital-FHIR-Genomics-ImplementationGuide/blob/04ab4bc353a3c002613c422ecfc9aea6ab38c1c7/documents/nhs-genomic-medicine-service-record-of-discussion-form.pdf), [Young Person Assent Form](https://github.com/NHSDigital/NHSDigital-FHIR-Genomics-ImplementationGuide/blob/f74753a2d203ceb0703f1acbbf85675bc0638f18/documents/nhs-genomic-medicine-service-young-persons-assent-form.pdf) or [Consultee Declaration Form](https://github.com/NHSDigital/NHSDigital-FHIR-Genomics-ImplementationGuide/blob/f74753a2d203ceb0703f1acbbf85675bc0638f18/documents/nhs-genomic-medicine-service-genomic-consultee-declaration-1.pdf). Within GMS payloads these are modelled as a QuestionnaireResponses, based upon the relevant FHIR {{pagelink:Home/Examples/Questionnaire}} resources.

It is expected that this QuestionnaireResponse will be wrapped/referenced from a Consent resource to capture the status of the discussion and categorise the consent as consent for research.

The use case for Genomics Consent for sharing data for research is as below:

|Name|Patient Consents to Genomics Testing Data Sharing|
|--|--|
|Description|This use case describes the process by which a patient consents to the sharing of their genomic data for clinical or research purposes. The consent decision must be recorded, stored, and accessible. This consent may later be revoked or updated by the patient.|
|Actors (Role)|Patient, Clinician, NHS Digital System (EHR, NHS Spine)|
|Frequency of Use|Whenever a patient is asked to provide consent for sharing their genomic data.|
|Triggers|The patient is asked to provide consent for sharing their genomic data.|
|Pre Conditions|The patient is undergoing genomic testing. <br>The patient has reviewed the genomics consent form|
|Post Conditions|The consent status is updated in the patient's EHR. <br>If approved, genomic data is shared where necessary. <br>If declined, no genomic data is shared beyond immediate care.|
|Main Course|1. The clinician discusses the genomic testing process with the patient. <br>2. The patient reviews the genomics consent form. <br>3. The patient agrees to share their genomic data for clinical purposes. <br>4. The clinician records the consent decision in the patient's EHR. <br>5. The consent is stored in the patient’s record and made available via NHS Spine.|
|Alternate Course|**A1: Patient Declines Consent** <br>1. If the patient declines, the system records a "rejected" status. <br>2. The patient's data is not shared for genomic research. <br>**A2: Patient Revokes Consent Later** <br>1. The patient accesses their consent record via a patient-facing portal. <br>2. They revoke their consent. <br>3. The system updates the consent status to "inactive" and prevents future data sharing.|
|Exception|The system is unavailable – consent is recorded manually and updated later. <br>The patient lacks capacity – consent is deferred or a legal proxy is consulted.|

**Scenarios**
* Patient Consent for Genomics Testing
Description: A patient is asked to consent to the sharing of their genomic data with healthcare organisations to facilitate genomic testing. (currently out of scope)

* Patient Consent for Genomics Research
Description: A patient is asked to consent to the storage and sharing of their genomic data for research purposes, potentially outside the immediate healthcare context.

* Young Person (6-15) Assent for Genomics Consent Decision by Parent
Description: A young person aged 6–15 completes an assent form, agreeing to allow their parent or legal guardian to make genomics-related consent decisions on their behalf.

* Consultee Provides Consent for National Genomic Research Library Participation
Description: A person, such as a legal representative, carer, or family member, is consulted to provide consent on behalf of a patient who is unable to make decisions independently (e.g. due to incapacity). This consent relates to the use of the patient's genomic data for participation in the National Genomic Research Library.

#### Consent Scopes
**Genomics Testing**

* **Comparison** - Patient data may be compared to other patients’ results across the country and internationally.
* **DNA Storage** - Normal NHS laboratory practice is to store the DNA extracted from my sample even after current testing is complete. Patient DNA might be used for future analysis and/or to ensure that other testing (for example that of family members) is of high quality.
* **Data Storage** - The data from a patient’s genomic test will be securely stored so that it can be looked at again in the future if necessary.
* **Health Records** - Results from a patient’s genomic test will be part of their patient record, a copy of which is held in a national system only available to healthcare professionals.

**The National Genomic Research Library (Optional)**

* **Data Access** - Genomics England can access a patient’s personal data including their genomic record.
* **Contact** – A patient’s clinical team or Genomics England together with their clinical team, can contact a patient if the data or samples reveal any clinical trials or other research that they might benefit from.
* **Collection** - Genomics England will collect different aspects of a patient’s health data from the NHS and other data from organisations listed at https://www.genomicsengland.co.uk/privacy-policy/. The collection and analysis of their health data for research will continue across their entire lifetime and beyond.

**Young Person Assent (6-15)**

* **Assent** – A young person (6-15) consents to their parent or guardian making decisions regarding the sharing of their genomic data.

**Consultee Consent**

* **National Genomic Research Library (NGRL)** – Consultee consents to the patient’s participation in the NGRL where approved researchers can access de-identified genomic data, health data and samples.

**References**

There are three different consent forms from which the above consent information has been taken:

1. [Record of Discussion form](https://github.com/NHSDigital/NHSDigital-FHIR-Genomics-ImplementationGuide/blob/04ab4bc353a3c002613c422ecfc9aea6ab38c1c7/documents/nhs-genomic-medicine-service-record-of-discussion-form.pdf)
2. [Young Person Assent Form](https://github.com/NHSDigital/NHSDigital-FHIR-Genomics-ImplementationGuide/blob/f74753a2d203ceb0703f1acbbf85675bc0638f18/documents/nhs-genomic-medicine-service-young-persons-assent-form.pdf)
3. [Consultee Declaration Form](https://github.com/NHSDigital/NHSDigital-FHIR-Genomics-ImplementationGuide/blob/f74753a2d203ceb0703f1acbbf85675bc0638f18/documents/nhs-genomic-medicine-service-genomic-consultee-declaration-1.pdf)

## Consent for the Unified Genomic Record

### Purpose-Based Access Control (Attribute-Based Access Control)

* PBAC ensures that genomic data access is controlled based on its intended use.
* Access control is categorised into two main areas:
    1. Access based on the characteristics of the user requesting access
        * This is based on **Role or Relationship to Patient** – Managed through CIS2 and NHS national roles (for NHS staff) and NHS App/Login (for patients and family) and validated proxy relationships.
        * Access is additionally restricted based on the **Purpose of access** – Differentiates access for Direct Care, Research, Population Health, and Management Information.
        * Access at this level is first determined via security tagging of resources to identify their sensitivity level. Their user type and purpose of access within their claim/auth token is then checked against the [IHE IUA](https://profiles.ihe.net/ITI/IUA/index.html) Authorisation and Resource Server to determine which resources can be returned to the user.
    2. Access based on the sharing preferences of the subject of the data
        * This uses the Consent resource as per the [Privacy Consent on FHIR (PCF) IHE Framework](https://profiles.ihe.net/ITI/PCF/) to additionally restrict access to certain resources, classes of resources, or sensitivity levels. 
        * An example of the Consent expected is provided at {{pagelink:Consent-UGRConsentForResearch-Example}} for a general consent to allow the full UGR to be used for research, and {{pagelink:Consent-UGRGenomicData-Example}} for consent to allow access to genomic data for population health, research and MI (NOTE: The IHE profiles do not currently support provisions on classes of data, only instances), for further examples of more advanced Consent provisions and how they should be used, please see the IHE PCF guide.
        * Provisions for classes of data SHOULD match the Composition sections as defined by the UGR working group to allow easy redaction of data, codes for these sections will be added to the FHIR IG for use in Compositions, as well as Consent resources, once these are mature.
        
The above categories determine what a user has access to and defines access granularity, such as test-based, Whole Genome Sequence (WGS), or historical test data.

### PBAC Access Categories
PBAC controls data access for four key use cases:

1. Direct Care – Default opt-in. Access is granted based on clinician role and patient relationship.
    - This is mapped to [ActReason](https://terminology.hl7.org/6.2.0/CodeSystem-v3-ActReason.html) TREAT
2. Population Health Management – Requires explicit opt-in.
    - This is mapped to [ActReason](https://terminology.hl7.org/6.2.0/CodeSystem-v3-ActReason.html) POPHLTH
3. Service Management (MI & Reporting) – Default opt-in.
    - This is mapped to [ActReason](https://terminology.hl7.org/6.2.0/CodeSystem-v3-ActReason.html) HOPERAT
4. Research (Clinical Trials, etc.) – Requires explicit opt-in.
    - This is mapped to [ActReason](https://terminology.hl7.org/6.2.0/CodeSystem-v3-ActReason.html) HRESCH

**Consent Models** - Patients may choose to opt in/out at a high level or set granular access rules for specific data sets.

### Granular Access Control
Different levels of access can be applied:

1. Full access to the UGR.
2. Access to specific data types (e.g. reports only).
3. Access to individual reports/tests.
4. Access to data elements within a resource (e.g. de-identified information).
5. Specialised access control is needed for raw genomic data, typically limited to Genomic Scientists.

Within the UGR alpha, only the top levels of granular access control will be investigated i.e. granting full access to the UGR for specific purposes, or granting access to specific classes of data.

### NHS Role-Based Access Control (RBAC) & PBAC
* NHS RBAC roles (e.g., Clinical Practitioner, Biomedical Scientist) determine access.
* There is an identified gap in RBAC role granularity, which may require further refinement to align with PBAC needs.

### Technology Considerations
* **FHIR-Based Consent Models** - Potential for FHIR Consent Profiles and [SMART on FHIR](https://www.hl7.org/fhir/smart-app-launch/index.html) for access control.
* **Cedar Policy Engine** - Used by Genomics England for policy management, an alternative to representing permissions/consent within FHIR.
* **OAuth2 & CIS2 Integration** - Possible use for managing user roles and activities dynamically, OAuth2 tokens can be used independently from CIS2. Authentication/authorisation methods for Genomic Services, especially where users do not have a CIS2 identity, or systems do not connect to CIS2 is still to be investigated.


