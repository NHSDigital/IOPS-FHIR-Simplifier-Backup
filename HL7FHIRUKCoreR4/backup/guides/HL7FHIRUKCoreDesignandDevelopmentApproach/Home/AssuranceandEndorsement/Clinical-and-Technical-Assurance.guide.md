# {{page-title}}

## Overview
This page details the Clinical and Technical Assurance process for the FHIR UK Core. 

A key part of the UK Core Clinical and Technical Assurance process is to ensure that any profiling of FHIR resources is done in a clinically safe and technically coherent manner.

---

## Why do we need a Clinical and Technical Assurance Process?
### Assets which are fit for purpose
The process will produce FHIR assets that are fit for purpose. The process encompasses clinical, clinical informatics, clinical safety, terminology, technical and vendor input. The key value added is multi-disciplinary collaboration in an agile team and the ability to improve quality of the product. Without the Clinical and Technical Assurance process, there is a risk that the hand over of requirements from business teams to the UK Core Development team to produce a specification might not meet wider business, clinical and technical requirements. 
### Engaging with system suppliers
Participation in the assurance process helps those who will be implementing the specifications understand the rationale and details behind the design. System suppliers are engaged as part of the process which gives them an opportunity to raise implementation issues and resolve them before the specifications are published. 
### Robust requirement definition
The process also challenges clinical requirements, should they be insufficiently detailed, resulting in a more robust requirement definition. The process provides a feedback loop to the business/programme team to update clinical requirements as needed.  
### FHIR asset consistency
The assurance process promotes consistency in FHIR assets across different healthcare programmes and use cases to support interoperability. There is a risk that programmes might develop FHIR assets which conflict with previous design decisions. This process ensures that the design decisions agreed previously are consistently applied, and any reasons for divergence are documented and justified in a transparent way. 

---

## What is FHIR Clinical and Technical Assurance?
In the FHIR Clinical and Technical Assurance process, a team of subject matter experts map use case specific clinical information models, for example, allergies and adverse reactions, to the AllergyIntolerance FHIR resource. This mapping produces a “profile” of the international base resource. During the mapping process, a variety of decisions are made, for example, relating to the use of appropriate terminology bindings, such as SNOMED CT. 

From a Clinical Assurance perspective, FHIR assets are reviewed for:
- Accuracy (clinical knowledge and clinical practices)
- Validity (designed correctly for the purpose of clinical practice and clinical use)
- Usability (useful and usable for the clinical story tested against)

From a Technical Assurance perspective, the FHIR assets are reviewed for:
- Conformance to the FHIR Standard
- Adherence to the documented guidance for Creating UK Core FHIR assets produced by the UK Core Development team
- Correct usage of the FHIR assets for the use case 

### Scope
#### In scope
The scope of the Clinical and Technical Assurance process is: 
- To provide collaborative opportunity to review FHIR resource usage, considering use case and data modelling requirements and to resolve any outstanding queries that may require further clarity
- To identify areas of data modelling that are inconsistent with current health informatics/clinical practices
- To assess FHIR resource proposals in relation to use case and architectural pattern for clinical risk
- To review proposed designs on how profiles reference/link with each other 
- To consider the mapping of proposed ValueSets to FHIR ValueSets as appropriate 
- To review alignment with the UK Core in terms of mappings, extensions and implementation guidance and highlight any deviation from the UK Core
- To review search parameters and trigger points relevant to the use case
#### Out of scope
The following activities are not in scope; it is assumed they are completed as pre-requisite:
- Validation of use cases and business processes 
- Validation of business data sets  
- Review of data model(s) with vendors 
### Clinical and Technical Assurance and UK Core Development and Release
Clinical and Technical assurance occurs during the UK Core development process. Selected UK Core assets at draft status must go through the assurance process in order to move to the status of Draft Standard for Trial Use (DSTU) prior to readiness for the HL7 ballot process.   
Find out more about the {{pagelink:UKCoreDevelopmentandReleaseManagement}}.

---

## How does the Clinical and Technical Assurance Process work?
The FHIR Clinical and Technical Assurance process includes six steps which are described below in which several programmes could run the process in parallel, thus improving the output of the process. The Clinical and Technical Assurance process team along with their roles and responsibilities for the process can be viewed in <a href="#appendixa">Appendix A</a>.

When profiles have been through the process once, it is expected that they will not need to go through the whole process again for every use case or programme. Once assured, profiles will be established as UK Core profiles, with business rules added to implementation guides for additional guidance. This will eventually shorten the process for all participants, as only new profiles will be discussed in detail. The change control and tracking of profiles and other FHIR assets will be managed by the UK Core development team.

   
### Key Steps in the Clinical and Technical Assurance process

### 1. Publication of the UK Core pack
This involves creating a UK Core pack for external consultation. 
#### Key Inputs
The following are key inputs to the creation of the UK Core pack:-
- Strategic overview to include background, scope, strategic objectives, vision and timelines
- Use cases, including description of clinical workflows and key interactions; see <a href="#appendixb"> Appendix B</a> for an example use case.
- Clinically assured Information models/datasets, including models from the <a href="https://theprsb.org"> Professional Record Standards Body (PRSB)</a>
- Patient journeys with example clinical content
- Architecture overview to include FHIR paradigm e.g. REST, bundle, document and transport layer e.g. MESH
- Initial list of FHIR resources for use cases
- Initial plan including deployment approach
- List of engaged vendors and representatives from a private beta site
#### Content of the UK Core pack
-  A first draft of the mapping of requirements to FHIR assets, including profiles, extensions, ValueSets, ConceptMaps, etc  by the UK Core team. 
-  Detailed comparisons between relevant UK Core R4 assets and CareConnect STU3 assets. See <a href="#appendixc">Appendix C</a> for more information.
- Comparison between R4 and R5 to understand the need for any backporting.
-  Data models/datasets
-  Design options; recommended options will be determined over several calls after external consultation 
-  Any associated implementation guides
-  Links to any useful training material

The UK Core pack will be created by the UK Core Development team. The pack will include design options; recommended options will be determined after external consultation. The UK Core Development team will create an itinerary to explain key decisions required from stakeholders. The current UK Core C&TA Documentation Pack can be found [here](https://simplifier.net/guide/UKCoreClinicalandTechnicalAssuranceDocumentationPack/Home?version=current).

### 2. External consultation
The UK Core pack will be released for consultation with external stakeholders for a period of 15 days with an ability to provide comments via Simplifier. The pack's release will be advertised on relevant channels e.g. email, Ryver, Simplifier news as appropriate.
Stakeholders will need to commit resources to attend team calls, which are scheduled once a week; this includes one external community call per sprint. 
After the review period, the UK Core Development team will review the comments and agree on resolutions which will be presented on a call to stakeholders. The scope of discussion on the consultation call is limited to the issues raised as review comments in the consultation phase. If there is no consensus on the consultation call, this will be escalated to the UK FHIR Delivery Senior Leadership Team (SLT) to make decisions.  This team will engage with the UK FHIR community and seek input as needed.  

### 3. Update specifications
The UK Core Development team will update the UK Core FHIR assets and associated guidance based on agreement on the external call or further agreement with the SLT, if required. 

### 4. Handover to the UK Core Change Control process

This will follow the change control process for the UK Core.  

### 5. Review and approve FHIR assets
The updated FHIR assets will be presented back to the community to approve confirm changes are as agreed in the external consultation, and have been correctly applied to the FHIR assets. Any final decisions needed will be agreed at the SLT. 


### 6. Produce hazard log and Clinical safety report

An initial hazard log will be produced in parallel as per the NHS England Clinical Safety process to identify any clinical risks associated with the proposed design and an associated clinical safety report will be produced. The hazard log and the clinical safety report will be presented to the NHS England Clinical Safety Group for endorsement.    

## Where do I start?

-  Anyone who is interested in developing new, or amending existing, FHIR assets should engage with the UK Core Development team.</a>.  
- If further clinical and technical assurance work is needed, the UK Core Development team will then start to prepare the schedule, including estimating the number of sprints required.
- The UK Core Development team will invite other stakeholders, such as terminologists, clinical safety representatives, clinicians, First of Type representatives and vendors to establish representation and availability for the process.


### Setting up meetings
-  The UK Core Development team will set up meetings and communicate with all potential participants. 
- The UK Core Development team will arrange all administration and organisation of agreed meetings. 

## What are the key outputs?

The example outputs of the process are:
- Assured UK Core profiles 
- Assured SNOMED CT/dm+d ValueSets/Refsets 
- Assured Implementation guidance 
- Agreed changes in the proposed business logical models 
- Clinical Safety Report and Hazard log

---

## How to get involved
### Via Simplifier 
- A list of all UKCore Implementation Guides, including draft guides can be found within the <a href="https://simplifier.net/guide/ukcoreversionhistory?version=current">UK Core Publication (Version) History</a>.
- All <a href="https://simplifier.net/HL7FHIRUKCoreR4/~resources?fhirstatus=Draft&category=Profile|ValueSet|CodeSystem|Extension|ConceptMap&fhirVersion=R4&sortBy=RankScore_desc">UK Core FHIR assets in Draft status</a> are also available.
- Any stakeholder can raise an issue in Simplifier relevant to these assets; see {{pagelink:Requests--Issues-and-Feedback}} for more information.

### Contact Us
If you require further information, please email the [UK Core Development team](mailto:interoperabilityteam@nhs.net).

---

<a id="appendixa"></a>
## Appendix A: Roles and Responsibilities
<a id="ukcoredevteam"></a>
### UK Core Development team:
This team is comprised of individuals who are involved in the UK Core FHIR assets development and/or authoring guidance contained in the UK Core Implementation Guide.
The main functions of this team are:-
- To publish FHIR assets and associated specifications.
- To update/maintain technical documentation in Simplifier 
- To prepare the core pack for calls/core team meetings to include profiling questions and technical options for decisions by stakeholders.
- To agree on the technical design decisions for changes to the UK Core profiles working in collaboration with stakeholders.
- To act as FHIR technical Subject Matter Expert (SME) to answer questions on FHIR constraints, proposed extensions and design principles
- To post on <a href="https://chat.fhir.org/">Zulip FHIR Chat</a> for feedback required and liaise with HL7 UK, if required.

### Project Manager (UK Core Development team or from the Programme/project):
- Lead on creation of review pack
- Publish draft agenda for the external calls
- To initiate MS teams, call and set it record
- Publish recordings
- Manage the schedule and pipeline working with the chair
- Action log reporting
- Track the delivery of: 
    - UK Core profiles 
    - Agreed SNOMED CT/dm+d value sets/refsets 
    - Implementation guidance 
    - Changes in the proposed information models 
    - Clinical safety report and hazard log

### Clinical Safety team
- To lead on identifying clinical safety issues in the workshop
- To develop and maintain a hazard log of clinical safety mapping issues to be addressed further by the group and / or in a clinical safety workshop
- To complete hazard log and clinical safety closure report for the process
- To obtain endorsement from the NHS England clinical safety group for the release of the specifications

### Terminologist: 
- To identify appropriate value set of SNOMED CT, including dm+d, or gaps, as required
- To explain the design principles of SNOMED CT value sets
- To agree on design decisions to use FHIR or SNOMED CT value sets
- To provide clinical terminology and clinical informatics advice

### Clinical Lead (Programme e.g. Digital Medicines):
- To present use cases including description of clinical workflows and key interactions. Provide Patient journeys with example clinical content
- Describe Information models/datasets 
- To inform clinical design decisions as part of the process: what might be the clinical safety implications on clinical workflows and clinical interpretation of data exchanged, when looking at the intended use of information models and the design principles of FHIR standards, and mapping decisions being made (clinical assurance)
- To provide a critical lens to question the real-world usefulness and safety implications of data identified in information models and exchanged using FHIR or SNOMED CT (clinical assurance)
- To help identify the risk of never events that might occur during the assurance of clinical information models onto the FHIR technical standard, and offering appropriate clinical safety mitigations (clinical assurance)

### FHIR Clinical Assurance Lead/Chair (Clinical Informatician with FHIR expertise):

- To lead on implementation of the clinical and technical assurance process
- To chair the UK core team meetings and external call and help prepare the review pack
- To ensure that the programme team and presenters are adequately prepared for the external call
- To work with the Project Manager on the pipeline and schedule of the future activities
- Manage the overall assurance process working with technical leads and look for improvement opportunities 

### Senior Clinical Lead (accountability):
- To provide overall clinical oversight to the process 
- To inform clinical design decisions (clinical assurance)

### Suppliers/Vendors:
- To inform design decisions on consultation calls 
- To provide practical real-world implementation insight (e.g. limitations, complexity)
- To inform assurance

### Technical Architect: 
- Inform the relevant programme of the new use case e.g. Digital Medicines and/or National capability e.g. national record locator 
- To provide technical architecture overview for the programme. 
- To answer any queries related to Technical architecture 

### Business Analyst (Programme e.g. Digital Medicines):
- To prepare use cases and clinical scenarios working with the programme clinical lead
- To understand and document use cases

---

<a id="appendixb"></a>
## Appendix B: Example use case 
### NHS Urgent Medicine Supply Advanced Service (NUMSAS)

|Use Case Key Area|Key Area further information|
|---
|**Use Case background**|<p>Over 7500 NUMSAS referrals occurred nationally in November 2017.</p><p> NHS111/IUC Clinical Assessment Service will refer patients to a community pharmacy (currently using an ITK or NH mail message).</p><p>If applicable the patient is supplied with the medicine/appliance by the pharmacy, details are recorded locally (electronically or on paper).</p><p>GP Practice is notified of the supply using electronic 'post event message' (currently email).</p>|
|**User Story**|<p>**As a** pharmacy contractor, **I can** notify the patient’s registered GP Practice of the emergency supply of a medicine/appliance, **so that** the details of the supply of the medicine/appliance is: </p><p>Received by the GP System of the patient’s registered GP Practice.</p><p>Integrated into the patient’s GP Record and/or GP workflow.</p>|
|**Current Process**|<p>Pharmacists may provide an emergency supply of a medicine/appliance to a patient, at the request of the patient or at the request of a prescriber.</p><p>The commissioning of emergency supplies varies. The emergency supply may be commissioned via a national NHS England service, locally commissioned, or may be paid for privately by the patient.</p><p>Community pharmacies legally must maintain a local record of an emergency supply of a medicine/appliance to a patient, which can be recorded electronically in a local pharmacy system or on paper.</p><p>The patient’s GP Practice may or may not be notified of the emergency supply, depending on the nature of the service.</p>|
|**Actors**|<p>Patient</p><p>Pharmacist – the individual who supplies the medicine(s) and records details of the emergency supply</p><p>MESH – Messaging System</p><p>(Sending) Pharmacy System – the pharmacy system where details of supply are recorded and which sends the supply information to the patient’s registered GP System</p><p>GP Practice System – the GP System of the patient’s registered GP Practice</p>|
|**Main Flow (this may vary according to the commissioned service)**|<ol><li> The Patient or Carer presents at the pharmacy.</li><li> The Pharmacist deems the request for emergency supply valid and appropriate and supplies the medicine/appliance(s), as per HMR.</li><li> The Pharmacist records the supply of the medicine/appliance(s) in the Pharmacy System, as specified in the applicable service specification/HMR.</li><li>The Pharmacy System sends the agreed detail of the emergency supply to the patient’s registered GP Practice System via MESH.</li><li>The GP Practice System receives the detail of the emergency supply of the medicine(s)</li><li>The GP Practice System integrates/includes details of the emergency supply or supplies into the patient’s GP Record and/or into the GP workflow. (Note, it is assumed that the supply information will be SNOMED coded where appropriate.)</li></ol>|
|**Alternates/ Exceptions**|<p>2a. The request for the emergency supply is invalid or inappropriate – no medicine/appliance(s) is/are supplied.</p><p>5a. The GP Practice System does not receive the supply information for some reason, e.g. the GP Practice System is not available.</p>|

---

<a id="appendixc"></a>
## Appendix C: STU3 CareConnect assets

The INTEROPen FHIR curation process assured the development of FHIR CareConnect assets in the FHIR STU3 version. These have been used as a reference point for the initial development of UK Core assets in FHIR R4. CareConnect profiles were previously classified to describe the level of constraints applied to them as follows:-
- Level 1: International FHIR baseline profile.
- Level 2: These are derived from Level 1 profiles and inherit all the constraints of Level 1 profiles. These are generic profiles and include country specific constraints e.g. NHS number, terminology bindings. 
- Level 3: These are derived from Level 2 profiles and inherit all the constraints of Level 2 profiles. Further constraints are applied at this level which are use case specific e.g. for Digital Child Health or Transfer of Care use cases. 

The links between FHIR resources, CareConnect profiles and FHIR UK Core profiles are described below in the diagram:

{{render:level-diagram}}

[CareConnect assets](https://simplifier.net/guide/hl7fhircareconnectprofilesstu3/Home) can be browsed online.
