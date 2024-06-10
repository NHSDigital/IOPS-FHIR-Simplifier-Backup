---
subject: https://fhir.nhs.uk/England/StructureDefinition/England-Patient-PDS
---

## {{page-title}}

### Register with a GP Surgery

The Register with a GP surgery service includes a set of mandated questions needed for patient registration with an NHS GP surgery. 

Patients are also asked a series of questions based on their personal circumstances. Where possible the service uses information that the NHS already knows about the patient to reduce the number of questions they have to answer.

The questions asked during the online registration process are all that are needed to successfully progress a patient registration.

It is not possible for a patient to leave mandatory fields unanswered as the service uses data validation. This means that even if a patient's registration contains unanswered questions you should still have all the necessary information you need to progress their registration.  

Here are the 4 categories of questions patients might come across:

1. Mandatory questions - these are essential questions asked to all patients.  

2. Optional health questions - all patients are asked these questions, but they are optional to answer.  

3. Extra questions - some patients may be asked extra questions based on their specific situation.  

4. Customised questions - questions tailored to individual patient needs and circumstances.

More details of the questions asked can be found on the [NHS Digital service pages](https://digital.nhs.uk/services/register-with-a-gp-surgery-service/get-help-using-the-service/questions-asked)


### Examples

Examples generated for the Register with a GP Surgery service are linked below, including the form definition.

{{pagelink:Register-with-a-GP-Surgery-Questionnaire}}

{{pagelink:Register-with-a-GP-Surgery-QuestionnaireResponse}}

{{pagelink:Register-with-a-GP-Surgery-Extracted-Resources}}


### Process Map

The expected end-to-end process for the Register with a GP Surgery is detailed below:

<plantuml>
@startuml

scale 1/2

title "Register with a GP Surgery "

participant "Patient" as Pat
participant "Register with a GP Surgery Service" as GPReg
participant "Personal Demographics Service" as PDS
participant "Multicast Notification Service" as MNS
participant "Winning GP Practice" as GPWin
participant "Losing GP Practice" as GPLos
participant "PCRM (NHAIS)" as PCRM

== Trigger GP Registration ==

Pat -> GPReg : Filled GP Reg Form
activate GPReg
Alt Auto Accept
GPReg -> PDS : FHIR Update Patient (mobile, landline, email, address)
activate PDS
PDS -> PDS : Update (address, contact)
deactivate PDS
GPReg -> MNS : Trigger Event (Registration Request)
activate MNS
MNS -> MNS : Create Event (Registration Request)
MNS -> GPWin : Event Notification (ASID, Type, NHS No, ODS Code)
activate GPWin
deactivate MNS
else Not Auto Accept
GPReg -> GPWin : Email
deactivate GPReg
end

== Create Patient ==

Alt NHSNo
GPWin -> PDS : FHIR Get Patient (NHS No)
activate PDS
PDS --> GPWin : Response (Name, DoB, Gender, Contact)
deactivate PDS
else Search
GPWin -> PDS : FHIR Search Patient (Demographic Details)
activate PDS
PDS --> GPWin : Response (Name, DoB, Gender, Contact)
deactivate PDS
end
deactivate GPWin

== BAU ==

GPWin -> PCRM : GPLinks (Patient Accepted)
activate PCRM
PCRM -> PCRM : Exception Check
PCRM -> PDS : HL7v3 Update (NHS No)
deactivate PCRM
GPWin -> GPLos : GP2GP (Get Record)
activate GPWin
activate GPLos
GPLos -> GPWin : GP2GP (Transfer Record)
deactivate GPLos
deactivate GPWin

@enduml
</plantuml>


### Resource Constraints

The Register with a GP Surgery Form has been represented through a {{pagelink:Home/FHIR-Assets/Profiles/Questionnaire.page.md}} resource, developed using the [LHC-Forms Form Builder Tool](https://lhncbc.nlm.nih.gov/LHC-research/LHC-projects/health-information/lhc-forms.html). 

**The draft Form Definition can be found on the [IOPS FHIR Development and Testing Tool](https://nhsdigital.github.io/interoperability-standards-tools-skunkworks/questionnaire?url=https:%2F%2Ffhir.nhs.uk%2FEngland%2FStructureDefinition%2FEngland-Questionnaire-RegisterGPSurgeryv2). It is expected this will be moved into an NHS England Forms Library once this has been developed. Please note that this definition is pending review from NHS England Data Standards and Terminology teams**

Filling of the form should result in a {{pagelink:Home/FHIR-Assets/Profiles/QuestionnaireResponse.page.md}} resource. Guidance on the generation of a QuestionnaireResponse resource for Structured Data Capture can be found on the {{pagelink:IHE-Structured-Data-Capture}} pages.

Individual questions can be extracted from the QuestionnaireResponse in the form of other clinical/administrative resources, e.g. Patient for demographic details and Observation for specific patient reported observations. Examples of the QuestionnaireResponse and extracted resources are linked from the {{pagelink:Home/Use-Cases/Patient-Registration/Services/Register-with-a-GP-Surgery/Examples.page.md}} page.

---

### New Patient Registration

#### Use Case

<table class="assets" title="PDS Use Case 1">
<td><strong>Name</strong></td><td>Create a record for a new patient</td>
</tr><tr>
<td><strong>Version</strong></td><td>0.1</td>
</tr><tr>
<td><strong>ID</strong></td><td>n/a</td></tr><tr><td><strong>Owner</strong></td><td>NHS England. <br>Team responsible for delivery – Demographics 101.</td>
</tr><tr>
<td><strong>User Story Summary (Clinical Overview)</strong></td><td><strong>As a</strong> PDS FHIR user with Healthcare Worker Access <br><strong>I want</strong> a new NHS number to be allocated for individuals, when no existing NHS number exists <br><strong>So that</strong> the individual's medical information can be attached to an NHS number</td>
</tr><tr>
<td><strong>Actors (Role)</strong></td><td>Healthcare professional (excluding GPs)</td></tr><tr><td><strong>Frequency of Use</strong></td><td>Used daily by multiple NHS trusts.</td>
</tr><tr>
<td><strong>Triggers</strong></td><td>Secondary healthcare provider searches for an individual (for example, using the 'Search for a patient' endpoint in the PDS FHIR API). If an NHS number is not found, then a request to allocate a new NHS number is submitted. Likely use cases for requesting a new NHS number through primary care are adoption, gender reassignment, unhoused individuals seeking medical care, or a new NHS number being required due to domestic violence or witness protection.</li><li>As part of a birth registration. 'Birth Notice allocation' (BNA) in NCRS (National Care Record Service) or the 'Birth Notice allocation endpoint in PDS HL7 is used for this.</li><li>For a visitor or migrant to the UK. NHS number will be created as part of the Home Office immigration data feed.</li></ol></td>
</tr><tr>
<td><strong>Pre Conditions</strong></td><td><ol><li>Patient is seeking medical care.</li><li>Patient's demographics information is known, such as name, gender, date of birth address, and communication details.</li><li>Healthcare work has attempted to locate Patient but has been unable to find an existing NHS number.</li></ol></td></tr><tr><td><strong>Post Conditions</strong></td><td>Patient's medical data can be attached to a NHS number on local systems.</td>
</tr><tr>
<td><strong>Main Course</strong></td><td>If no NHS number exists for the submitted individual, a new NHS number is allocated and returned to the user.</td>
</tr><tr>
<td><strong>Alternate Course</strong></td><td>If a single NHS number exists for the supplied demographic data, then this found NHS number is returned to the user.</td></tr><tr><td><strong>Exception</strong></td><td>If multiple NHS numbers are found for the supplied demographic data, then an error message is returned to the user.</td>
</tr></tbody></table>

---

#### Process Map

This page is to aid vendors in creating a new patient within PDS.

<table class="assets" title="PDS New Patient Framework, interaction and profile">
<tr>
<th>Framework</th>
<th>FHIR Interaction</th>
<th>FHIR Profile</th>
</tr>
<tr>
<td><a href="https://profiles.ihe.net/ITI/PIXm/">IHE PIXm</a></td>
<td><a href="https://hl7.org/fhir/R4/http.html">RESTful API</a></td>
<td>{{pagelink:Profile-England-Patient-PDS}}</td>
</tr>
</table>

<plantuml>
@startuml


title NHS Number Allocation

start
:NHS Number Allocation Request;
switch (Existing PDS record found?)
case ( Found )
  :Response with error code;
case ( Not found )
  :Create PDS record;
endswitch
stop

@enduml
</plantuml>

<plantuml>
@startuml

hide footbox

title "Patient Identity Feed plus Notifications"

participant "PDS Consumer Source" as PIXSource
participant "PDS" as PIXManager

PIXSource -> PIXManager :  PDS Advanced Trace Querys
PIXManager --> PIXSource : Response
opt No matching Patient
  PIXSource -> PIXManager: PDS NHS Number Allocation Request
  PIXManager --> PIXSource : PDS NHS Number Allocation Request Accepted/Rejected
else Matching Patient - Update Demographics
  PIXSource -> PIXManager: PDS Updating patient details
  PIXManager --> PIXSource : Response
end


@enduml
</plantuml>

---

#### Patient Constraints

{{page:Home/Templates/Mandatory-Template.page.md}}


---

#### Examples


{{pagelink:Home/FHIR-Assets/Examples/New-patient-with-Minimum-Information-Required.page.md}}

{{pagelink:Home/FHIR-Assets/Examples/New-patient-with-Interpreter-Required.page.md}}

---

### Programmes

#### Personal Demographic Service (PDS)
Access patients' personal information, such as name, address, date of birth, related people, registered GP, nominated pharmacy and NHS number using the FHIR version of the Personal Demographics Service API.

[Personal Demographics Service- FHIR API](https://digital.nhs.uk/developer/api-catalogue/personal-demographics-service-fhir)

---
