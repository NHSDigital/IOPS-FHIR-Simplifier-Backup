# {{page-title}}

## Overview
This page details the Clinical and Technical Assurance process for the NHS England Implementation Guide
A key part of the NHS England Clinical and Technical Assurance process is to ensure that any profiling of FHIR resources is done in a clinically safe and technically coherent manner and is UK Core conformant.

The IOPS team will manage a regular Clinical and Technical Assurance (C&TA) review cycle, which will allow stakeholders, including programmes, a chance to propose and review changes to the NHS England IG before the release of a live version,(e.g. 1.0.0 pre-release version of NHSE IG - SIMPLIFIER.NET)

The exact timescale and scope for the C&TA sprints is yet to be determined.


## Why do we need a Clinical and Technical Assurance Process?

### Assets which are fit for purpose
The process will produce FHIR assets that are fit for purpose for NHS England requirements. The process encompasses clinical, clinical informatics, clinical safety, terminology and technical input. The key value added is multi-disciplinary collaboration in an agile team and the ability to improve quality of the product. Without the Clinical and Technical Assurance process, there is a risk that the handover of requirements from business teams to the IOPS team to produce a specification might not meet wider business, clinical and technical requirements across NHS England programs.

### Engaging with system suppliers
The NHS England Clinical and Technical Assurance is an internal process for NHS England and vendor input should be via NHS England programs.

### Robust requirement definition

The process also challenges clinical requirements, should they be insufficiently detailed, resulting in a more robust requirement definition. The process provides a feedback loop to the business/programme team to update clinical requirements as needed. The requirements need to be defined at an NHS England level not individual program level.

### FHIR asset consistency

The assurance process promotes consistency in FHIR assets across different healthcare programmes and use cases to support interoperability. There is a risk that programmes might develop FHIR assets which conflict with previous design decisions. This process ensures that the design decisions agreed previously are consistently applied, and any reasons for divergence are documented and justified in a transparent way. FHIR assets should be UK Core unless there is a valid requirement to create NHS England constrained version.
________________________________________
## What is FHIR Clinical and Technical Assurance?
In the FHIR Clinical and Technical Assurance process, a team of subject matter experts map use case specific clinical information models from NHS England program a to define if and what constraints are needed on the UK Core for these use cases. This mapping may produce a “profile” of the UK Core profile. During the mapping process, a variety of decisions are made, for example, relating to the use of appropriate terminology bindings, such as SNOMED CT.

From a Clinical Assurance perspective, FHIR assets are reviewed for:
- Accuracy (clinical knowledge and clinical practices)
- Validity (designed correctly for the purpose of clinical practice and clinical use)
- Usability (useful and usable for the clinical story tested against)
- Whether they provide enough extra constraint over the UK Core to make them worth while

From a Technical Assurance perspective, the FHIR assets are reviewed for:
- Conformance to the FHIR Standard and UK Core
- Adherence to the documented guidance for Creating NHS England FHIR assets produced by the IOPS Team
- Correct usage of the FHIR assets for the use case

## Scope
### In scope
The scope of the Clinical and Technical Assurance process is:
- To provide collaborative opportunity to review NHS England FHIR resource usage, considering use case and data modelling requirements and to resolve any outstanding queries that may require further clarity
- To identify areas of data modelling that are inconsistent with current health informatics/clinical practices
- To assess FHIR resource proposals in relation to use case and architectural pattern for clinical risk
- To review proposed designs on how profiles reference/link with each other
- To consider the mapping of proposed ValueSets to FHIR ValueSets as appropriate
- To review alignment with the UK Core in terms of mappings, extensions and implementation guidance and highlight any deviation from the UK Core so that it can be resolved.
- To review search parameters and trigger points relevant to the use case

### Out of scope
The following activities are not in scope; it is assumed they are completed as pre-requisite:
- Validation of use cases and business processes
- Validation of business data sets
- Review of data model(s) 

## Clinical and Technical Assurance and NHS England IG release
Clinical and Technical assurance occurs during the NHS England development process. Selected NHS England assets at draft status must go through the assurance process in order to move to the status active.

Find out more about the [Development and Release Management](https://simplifier.net/guide/nhs-england-design-and-development-approach/Home/Management/Development-and-Release-Management?version=current).
________________________________________
### How does the Clinical and Technical Assurance Process work?
The FHIR Clinical and Technical Assurance process includes six steps which are described below. The Clinical and Technical Assurance process team comprises of clinical leads, clinical informaticians, message modellers, terminology specialists, clinical safety staff. When profiles have been through the process once, it is expected that they will not need to go through the whole process again for every use case or programme. Once assured, profiles will be established as NHS England profiles, with business rules added to implementation guides for additional guidance. This will eventually shorten the process for all participants, as only new profiles will be discussed in detail. The change control and tracking of profiles and other FHIR assets will be managed by the IOPS team.

### Main Roles in the Clinical and Technical Assurance Process

Roles may include, but may not be limited to:-
- Clinical Leads
- Clinical Informaticians
- Clinical Safety
- Terminologist
- Architect
- Business analyst
- Project manager
- IOPS Team

The roles and responsibilities for the process can be viewed in [Appendix A](https://simplifier.net/guide/NHSE-Design-and-Development-Approach2/Home/Assurance---Endorsement/Clinical-and-Technical-Assurance.page.md?version=current).

### Key Steps in the Clinical and Technical Assurance process
The diagram describes the key steps in the process and each step is described in more detail below.

### Publication of the NHS England pack (1.0)
This involves creating a NHS England pack for consultation.
#### Key Inputs

The following are key inputs to the creation of the NHS England pack:-

- Strategic overview to include background, scope, strategic objectives, vision and timelines
- Use cases, including description of clinical workflows and key interactions; see [Appendix B](https://simplifier.net/guide/NHSE-Design-and-Development-Approach2/Home/Assurance---Endorsement/Clinical-and-Technical-Assurance.page.md?version=current) for an example use case.
- Clinically assured Information models/datasets, including models from the Professional Record Standards Body [(PRSB)](https://theprsb.org/)
- Patient journeys with example clinical content
- Architecture overview to include FHIR paradigm e.g. REST, bundle, document and transport layer e.g. MESH
- Initial list of FHIR resources for use cases

#### Content of the NHS England pack
- A first draft of the mapping of requirements to FHIR assets, including profiles, extensions, ValueSets, ConceptMaps, etc by the IOPS Team
- Detailed comparisons between relevant UK Core R4 assets and NHS proposed FHIR Assets
- Design options; recommended options will be determined over several calls after consultation
- Any associated implementation guides
- Links to any useful training material

The NHS England pack will be created by the IOPS Team. The pack will include design options; recommended options will be determined after external consultation. The IOPS will create an itinerary to explain key decisions required from stakeholders.

### External consultation (2.0)
The NHS England pack will be released for consultation with external stakeholders for a period of no more than 5 days with an ability to provide comments via Simplifier. The pack's release will be advertised on relevant channels e.g. email, , Simplifier news as appropriate. Stakeholders will need to commit resources to attend any team calls. After the review period, the IOPS Team will review the comments and agree on resolutions which will be presented on a call to stakeholders. The scope of discussion on the consultation call is limited to the issues raised as review comments in the consultation phase. If there is no consensus on the consultation call, this will be escalated to the FHIR product owner and other suitable NHS England personnel make the decision.

### Update specifications (3.0)
The IOPS Team will update the NHS England FHIR assets and associated guidance based on agreement on the call.

### Handover to the NHS England Change Control process (4.0)
This will follow the change control process for the NHS England.

### Review and approve FHIR assets (5.0)
The updated FHIR assets will be presented back to the NHS England stakeholders to approve confirm changes are as agreed in the external consultation, and have been correctly applied to the FHIR assets. 

### Produce hazard log and Clinical safety report (6.0)
An initial hazard log will be produced in parallel as per the NHS England Clinical Safety process to identify any clinical risks associated with the proposed design and an associated clinical safety report will be produced. The hazard log and the clinical safety report will be presented to the NHS England Clinical Safety Group for endorsement.

## Where do I start?
- Anyone who is interested in developing new, or amending existing, FHIR assets should engage with the IOPS Team to discuss the creation of a pack using the agreed template.
- If further clinical and technical assurance work is needed, the IOPS team will then start to prepare the schedule, including estimating the number of sprints required.
- The IOPS Team will invite other stakeholders, such as terminologists, clinical safety representatives, clinicians as it sees fit.

## Setting up meetings
- The IOPS Team will set up meetings and communicate with all potential participants.
- The IOPS team will arrange all administration and organisation of agreed meetings.

### What are the key outputs?
The example outputs of the process are:
- Assured NHS England profiles
- Assured SNOMED CT/dm+d ValueSets/Refsets
- Assured Implementation guidance
- Agreed changes in the proposed business logical models
- Clinical Safety Report and Hazard log
________________________________________
### How to get involved

Via Simplifier
- A list of all NHS England Implementation Guides, including draft guides can be found within the NHS England Version History
- Any stakeholder can raise an issue in Simplifier relevant to these assets; you need a Simplifier account to do this. You can register at https://simplifier.net/signup.
Contact Us

If you require further information, please email the [IOPS Team]( mailto:interoperabilityteam@nhs.net).


<!-- 
##### RM: This does not give any info on the C&TA - removed to ensure this page is kept concise and on topic #####

## Background
### Health Level Seven International
Founded in 1987, <a href="https://www.hl7.org/">Health Level Seven International (HL7)</a> is a not-for-profit, ANSI-accredited, healthcare standards developing organisation. <a href="https://www.hl7.org.uk/">HL7 UK</a> is the UK affiliate organisation to HL7 International and was set up in January 2000.
### Fast Healthcare Interoperability Resources (FHIR®)
<a href="https://hl7.org/fhir/">Fast Healthcare Interoperability Resources (FHIR®)</a> is a next generation standards framework created by HL7. FHIR combines the best features of HL7's v2, v3 and Clinical Document Architecture (CDA) product lines while leveraging the latest web standards and applying a tight focus on implementability. FHIR solutions are built from a set of modular components called "Resources". These resources can easily be assembled into working systems that solve real world clinical and administrative problems at a fraction of the price of existing alternatives.   
The current published version of FHIR is Release 4, which was published in December 2018. This was preceded by the version Standards in Trial Use (STU3). The FHIR [Directory of Published versions](http://hl7.org/fhir/directory.html) lists all versions.
### Other National FHIR "Core" developments
The FHIR UK Core has been preceded by the development of other national FHIR "Core" assets, for example the <a href="https://www.hl7.org/fhir/us/core/">US Core</a>.
### FHIR Profiling
A FHIR profile is a set of constraints on a resource. A "constraint" specifies a set of restrictions on the content of a FHIR resource or data type, or an additional set of constraints on an existing profile, for example:- 
- Changing the cardinality of the element; e.g. the base might allow 0..*, and a particular application might support 1..2
- Restricting the contents of an element to a single fixed value
- Specifying a binding to a different ValueSet
- Declaring that one or more elements in the structure must be 'supported'.

Further details of the above concepts relating to [FHIR profiling](http://hl7.org/fhir/r4/profiling.html) and 
[binding](https://www.hl7.org/fhir/r4/terminologies.html#strength) for terminologies used with FHIR assets is available.   -->
A key part of the NHS England IG Clinical and Technical Assurance process is to ensure that any profiling of FHIR resources is done in a clinically safe and technically coherent manner.

<!-- ##### RM: This does not give any info on the C&TA - removed to ensure this page is kept concise and on topic #####
### INTEROPen FHIR Curation process
The UK Core FHIR Clinical and Technical Assurance process builds on a previous process, known as the INTEROPen FHIR curation process, and includes changes to align it with the new UK Core approach. -->

---

## Why do we need a Clinical and Technical Assurance Process?
### Assets which are fit for purpose
The process will produce FHIR assets that are fit for purpose. The process encompasses clinical, clinical informatics, clinical safety, terminology, technical and vendor input. The key value added is multi-disciplinary collaboration in an agile team and the ability to improve quality of the product. Without the Clinical and Technical Assurance process, there is a risk that the hand over of requirements from business teams to the IOPS Team to produce a specification might not meet wider business, clinical and technical requirements. 
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
- Adherence to the documented guidance for Creating NHS England IG FHIR assets produced by the IOPS Team
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
### Clinical and Technical Assurance and NHS England IG Development and Release
Clinical and Technical assurance occurs during the NHS England IG development process. Selected NHS England IG assets at draft status must go through the assurance process in order to move to the status of Draft Standard for Trial Use (DSTU) prior to readiness for the HL7 ballot process.   
Find out more about NHS England [Release management](https://simplifier.net/guide/NHSE-Design-and-Development-Approach2/Home/Management/Development-and-Release-Management?version=current).


<!-- ##### RM: Removed as duplicating info from  UKCoreDevelopmentandReleaseManagement (link above) #####

#### Physical Delivery of UK Core assets
The FHIR UK Core pack and downloadable FHIR assets will be created with FHIR tooling using a platform called Simplifier. 
-->

---

## How does the Clinical and Technical Assurance Process work?
The FHIR Clinical and Technical Assurance process includes six steps which are described below. The Clinical and Technical Assurance process team comprises of clinical leads, clinical informaticians, message modellers, terminology specialists, clinical safety staff, First of Type (FoT) representatives from programmes, implementers and vendors and information governance representatives (if needed).
Note that several programmes could run the process in parallel, so improving the output of the process. When profiles have been through the process once, it is expected that they will not need to go through the whole process again for every use case or programme. Once assured, profiles will be established as NHS England IG profiles, with business rules added to implementation guides for additional guidance. This will eventually shorten the process for all participants, as only new profiles will be discussed in detail. The change control and tracking of profiles and other FHIR assets will be managed by the IOPS Team.

### Main Roles in the Clinical and Technical Assurance Process
Roles may include, but may not be limited to:-
-  Clinical Leads
-  Clinical Informaticians
-  Clinical Safety
-  Terminologist
-  Suppliers or vendors
-  Architect
-  Business analyst
-  Project manager
-  IOPS Team 

The roles and responsibilities for the process can be viewed in <a href="#appendixa">Appendix A</a>.   
### Key Steps in the Clinical and Technical Assurance process
The link mentioned below describes the key steps in the process and each step is described in more detail.  Please note that access to this diagram will require NHS.net login
<a href="https://nhs.sharepoint.com/sites/msteams_67ef67/Shared%20Documents/Forms/AllItems.aspx?id=%2Fsites%2Fmsteams%5F67ef67%2FShared%20Documents%2FProducts%2C%20Projects%2C%20and%20Programmes%2FNHS%20England%20IG%2FNHSEAssurance%2Epng&viewid=8b8148e1%2Da3a1%2D434d%2Da750%2D0986267b189d&parent=%2Fsites%2Fmsteams%5F67ef67%2FShared%20Documents%2FProducts%2C%20Projects%2C%20and%20Programmes%2FNHS%20England%20IG">ClinicalandTechnicalAssuranceProcess</a>

The diagram describes the overview of the process.

{{render:ClinicalandTechnicalAssuranceProcess}}

### Publication of the NHS England IG pack (1.0)
This involves creating a NHS England IG pack for external consultation. 
#### Key Inputs
The following are key inputs to the creation of the NHS England IG pack:-
- Strategic overview to include background, scope, strategic objectives, vision and timelines
- Use cases, including description of clinical workflows and key interactions; see <a href="#appendixb"> Appendix B</a> for an example use case.
- Clinically assured Information models/datasets, including models from the <a href="https://theprsb.org"> Professional Record Standards Body (PRSB)</a>
- Patient journeys with example clinical content
- Architecture overview to include FHIR paradigm e.g. REST, bundle, document and transport layer e.g. MESH
- Initial list of FHIR resources for use cases
- Initial plan including deployment approach
- List of engaged vendors and representatives from a private beta site
#### Content of the NHS England IG pack
-  A first draft of the mapping of requirements to FHIR assets, including profiles, extensions, ValueSets, ConceptMaps, etc  by the IOPS team. 
-  Detailed comparisons between relevant NHS England IG R4 assets and CareConnect STU3 assets. See <a href="#appendixd">Appendix D</a> for more information.
-  Data models/datasets
-  Design options; recommended options will be determined over several calls after external consultation 
-  Any associated implementation guides
-  Links to any useful training material

The NHS IG pack will be created by the IOPS Team. The pack will include design options; recommended options will be determined after external consultation. The IOPS Team will create an itinerary to explain key decisions required from stakeholders. 

### External consultation (2.0)
The NHS IG pack will be released for consultation with external stakeholders for a period of 15 days with an ability to provide comments via Simplifier. The pack's release will be advertised on relevant channels e.g. email, Ryver, Simplifier news as appropriate.
Stakeholders will need to commit resources to attend team calls, which are scheduled once a week; this includes one external community call per sprint. 
After the review period, the IOPS Team will review the comments and agree on resolutions which will be presented on a call to stakeholders. The scope of discussion on the consultation call is limited to the issues raised as review comments in the consultation phase. If there is no consensus on the consultation call, this will be escalated to the UK FHIR Delivery Senior Leadership Team (SLT) to make decisions.  This team will engage with the UK FHIR community and seek input as needed.  

### Update specifications (3.0) 
The IOPS Team will update the NHS England IG FHIR assets and associated guidance based on agreement on the external call or further agreement with the SLT, if required. 

### Handover to the NHS England IG Change Control process (4.0)

This will follow the change control process for the NHS England IG.  
### Review and approve FHIR assets (5.0)
The updated FHIR assets will be presented back to the community to approve confirm changes are as agreed in the external consultation, and have been correctly applied to the FHIR assets. Any final decisions needed will be agreed at the SLT. 


### Produce hazard log and Clinical safety report (6.0)

An initial hazard log will be produced in parallel as per the NHS England Clinical Safety process to identify any clinical risks associated with the proposed design and an associated clinical safety report will be produced. The hazard log and the clinical safety report will be presented to the NHS England Clinical Safety Group for endorsement.    

## Where do I start?

-  Anyone who is interested in developing new, or amending existing, FHIR assets should engage with the IOPS Team to prepare a pack using the Core Pack template which is available in <a href="#appendixc" >Appendix C</a>.  
- If further clinical and technical assurance work is needed, the IOPS Team will then start to prepare the schedule, including estimating the number of sprints required.
- The IOPS Team will invite other stakeholders, such as terminologists, clinical safety representatives, clinicians, First of Type representatives and vendors to establish representation and availability for the process.


### Setting up meetings
-  The IOPS Team will set up meetings and communicate with all potential participants. 
- The IOPS Team will arrange all administration and organisation of agreed meetings. 

## What are the key outputs?

The example outputs of the process are:
- Assured NHS England IG profiles 
- Assured SNOMED CT/dm+d ValueSets/Refsets 
- Assured Implementation guidance 
- Agreed changes in the proposed business logical models 
- Clinical Safety Report and Hazard log

---

## How to get involved
### Via Simplifier 
- A list of all NHS England IG Implementation Guides, including draft guides can be found within the <a href="https://simplifier.net/guide/nhs-england-implementation-guide-version-history?version=current">NHS England Implementation Guide Version History </a>.
- All <a href="https://simplifier.net/NHS-England-Implementation-Guide/~resources?fhirstatus=Draft&category=Profile|ValueSet|CodeSystem|Extension|CapabilityStatement|NamingSystem|Example&fhirVersion=R4&sortBy=RankScore_desc">NHS England IG FHIR assets in Draft status</a> are also available.
- Any stakeholder can raise an issue in Simplifier relevant to these assets; you need a Simplifier account to do this. You can register at https://simplifier.net/signup.

### Contact Us
If you require further information, please email the [IOPS Team](mailto:interoperabilityteam@nhs.net).

---

## Appendix A: Roles and Responsibilities
### IOPS Team:

This team is comprised of individuals who are involved in the NHS England FHIR assets development and/or authoring guidance contained in the NHS England Implementation Guide. 

The main functions of this team are:-
- To publish FHIR assets and associated specifications.
- To update/maintain technical documentation in Simplifier
- To prepare the core pack for calls/core team meetings to include profiling questions and technical options for decisions by stakeholders.
- To agree on the technical design decisions for changes to the NHS England profiles working in collaboration with stakeholders.
- To act as FHIR technical Subject Matter Expert (SME) to answer questions on FHIR constraints, proposed extensions and design principles
- To post on [Zulip FHIR Chat](https://chat.fhir.org/) for feedback required and liaise with HL7 UK, if required.
- To Liaise with the IOPS Team where required. 

### Project Manager (IOPS Team):

- Lead on creation of review pack
- Publish draft agenda for the required calls
- To initiate MS teams, call and set it record
- Publish recordings
- Manage the schedule and pipeline working with the chair
- Action log reporting
- Track the delivery of:
- NHS England profiles
- Agreed SNOMED CT/dm+d value sets/refsets
- Implementation guidance
- Changes in the proposed information models
- Clinical safety report and hazard log
- Alignment and conformance with UK Core

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

### FHIR Assurance Chair (IOPS Senior member):

- To lead on implementation of the clinical and technical assurance process
- To chair the NHS England team meetings and any calls and help prepare the review pack
- To ensure that the programme team and presenters are adequately prepared for the external call
- To work with the Project Manager on the pipeline and schedule of the future activities
- Manage the overall assurance process working with technical leads and look for improvement opportunities

### Senior Clinical Lead (accountability):

- To provide overall clinical oversight to the process
- To inform clinical design decisions (clinical assurance)

### Technical Architect:

- Inform the relevant programme of the new use case e.g. Digital Medicines and/or National capability e.g. national record locater
- To provide technical architecture overview for the programme.
- To answer any queries related to Technical architecture
- To ensure that the uses case and solutions meet any strategic view 

### Business Analyst (Programme e.g. Digital Medicines):

- To prepare use cases and clinical scenarios working with the programme clinical lead
- To understand and document use cases
________________________________________
## Appendix B: Example use case
NHS Urgent Medicine Supply Advanced Service (NUMSAS)

Over 7500 NUMSAS referrals occurred nationally in November 2017.
NHS111/IUC Clinical Assessment Service will refer patients to a community pharmacy (currently using an ITK or NH mail message).

If applicable the patient is supplied with the medicine/appliance by the pharmacy, details are recorded locally (electronically or on paper).
GP Practice is notified of the supply using electronic 'post event message' (currently email).

### User Story	

As a pharmacy contractor, I can notify the patient’s registered GP Practice of the emergency supply of a medicine/appliance, so that the details of the supply of the medicine/appliance is:

- Received by the GP System of the patient’s registered GP Practice.
- Integrated into the patient’s GP Record and/or GP workflow.

#### Current Process	

Pharmacists may provide an emergency supply of a medicine/appliance to a patient, at the request of the patient or at the request of a prescriber.
The commissioning of emergency supplies varies. The emergency supply may be commissioned via a national NHS England service, locally commissioned, or may be paid for privately by the patient.
Community pharmacies legally must maintain a local record of an emergency supply of a medicine/appliance to a patient, which can be recorded electronically in a local pharmacy system or on paper.
The patient’s GP Practice may or may not be notified of the emergency supply, depending on the nature of the service.

**Actors**	
- Patient
- Pharmacist – the individual who supplies the medicine(s) and records details of the emergency supply
- MESH – Messaging System
- (Sending) Pharmacy System – the pharmacy system where details of supply are recorded and which sends the supply information to the patient’s registered GP System
- GP Practice System – the GP System of the patient’s registered GP Practice

**Main Flow** (this may vary according to the commissioned service)	

1.	The Patient or Carer presents at the pharmacy.
2.	The Pharmacist deems the request for emergency supply valid and appropriate and supplies the medicine/appliance(s), as per HMR.
3.	The Pharmacist records the supply of the medicine/appliance(s) in the Pharmacy System, as specified in the applicable service specification/HMR.
4.	The Pharmacy System sends the agreed detail of the emergency supply to the patient’s registered GP Practice System via MESH.
5.	The GP Practice System receives the detail of the emergency supply of the medicine(s)
6.	The GP Practice System integrates/includes details of the emergency supply or supplies into the patient’s GP Record and/or into the GP workflow. (Note, it is assumed that the supply information will be SNOMED coded where appropriate.)
Alternates/ Exceptions	2a. The request for the emergency supply is invalid or inappropriate – no medicine/appliance(s) is/are supplied.
5a. The GP Practice System does not receive the supply information for some reason, e.g. the GP Practice System is not available.

