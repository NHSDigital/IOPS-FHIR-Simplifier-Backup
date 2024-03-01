## {{page-title}}

### [Link to the High Fidelity Wireframe for Duo/Trio testing (family sample)](https://cts5j3.axshare.com/)

The following steps is a walk through of:

### 1. Requester searches for a patient (a dummy patient has been pre-populated as an example)

**Params:**
```
given=Phoebe
family=Smitham
birthdate=eq2013-09-27
```

**Response:**

{{pagelink:Patient-PheobeSmitham-Example}}

### 2. Requester selects appropriate code. In this scenario, the example used is Likely Inborn Metabolism (R98)

Saved under ServiceRequest.code

### 3. Requester completes the Test Order Form and indicates family members ROD and sample associated to the test request

POST of Test order transaction Bundle for Pheobe Smitham consisting of the following resources: 

{{pagelink:Patient-PheobeSmitham-Example}}

{{pagelink:Observation-AutisticBehaviour-Example}}

{{pagelink:Observation-DelayedSpeechLanguageDevt-Example}}

{{pagelink:Observation-DiseasePenetrancePheobeSmitham-Example}}

{{pagelink:Observation-IntellectualDisabilityProfound-Example}}

{{pagelink:Observation-NonConsanguinousUnionProband-Example}}

{{pagelink:PractitionerRole-EugeneSmithLeedsSTH-Example}}

{{pagelink:ServiceRequest-WGSTestOrderForm-TrioTestingProband-Example}}

{{pagelink:Specimen-PheobeSmitham-Example}}


Details for Mother added to request:

{{pagelink:Patient-PheobeSmithamMother-Example}}

{{pagelink:RelatedPerson-AliceSmithamProbandMother-Example}}

{{pagelink:Specimen-PheobeSmithamMother-Example}}

{{pagelink:FamilyMemberHistory-NonConsanguinousUnionProbandMother-Example}}

{{pagelink:Observation-NonConsanguinousUnionProbandMother-Example}}

{{pagelink:Observation-NoTransfusionProbandMother-Example}}

{{pagelink:Observation-NoBoneMarrowTransplantProbandMother-Example}}


Details for Father added to request (sample not collected at time of submission):

{{pagelink:Patient-PheobeSmithamFather-Example}}

{{pagelink:RelatedPerson-JamesLawrenceProbandFather-Example}}

{{pagelink:FamilyMemberHistory-NonConsanguinousUnionProbandFather-Example}}

{{pagelink:Observation-NonConsanguinousUnionProbandFather-Example}}

{{pagelink:Observation-NoTransfusionProbandFather-Example}}

{{pagelink:Observation-NoBoneMarrowTransplantProbandFather-Example}}

{{pagelink:Observation-IntellectualDisabilityMild-Example}}


Record of Discussion form resources added to request (YPA and CD forms for Pheobe Smitham and RoD for the Mother, Father's RoD/consent not collected at time of submission):

{{pagelink:Consent-RoD-PheobeSmitham-Example}}

{{pagelink:Consent-RoD-PheobeSmithamYoungPersonAssentForm-Example}}

{{pagelink:Consent-RoD-PheobeSmithamMother-Example}}

{{pagelink:QuestionnaireResponse-RoD-PheobeSmithamCDForn-Example}}

{{pagelink:QuestionnaireResponse-RoD-PheobeSmithamYPAForm-Example}}

{{pagelink:Consent-RoD-PheobeSmithamMother-Example}}


### 4. Requester indicates that sample is going to be collected at a later date

Indicated through absence of Specimen resource in message or absence of ```Specimen.collectedDateTime```/```Specimen.status=unavailable``` for appropriate specimen

### The lab recieves the test request and:

### 1. Views the completed test order form

Obtained through GET /ServiceRequest or /GET Task requests (using params on {{pagelink:Home/FHIRAssets/CapabilityStatements}} to filter results) for non-routed requests. (Dashboard of available requests)

OR

Obtained through GET /Task request (filtered by GLH owner) for routed requests.

Then

GET /Task by Id and referenced ServiceRequest for view of individual.

### 2. Indicates awaiting sample/ ROD from father and changes request to awaiting further information

POST of {{pagelink:Task-WGSRareDiseaseTestOrderHold-TrioTestingProband-Example}}

### 3. When all samples/ ROD arrives at the lab, test request is triaged and accepted

Receipt of: 

{{pagelink:Home/Examples/Consent/Consent-RoD-PheobeSmithamFather-Example.page.md}} (wrapper for RoD)

{{pagelink:QuestionnaireResponse-RoD-PheobeSmithamFather-Example}} (RoD if collected as structured QuestionnaireResponse)

{{pagelink:Specimen-PheobeSmithamFather-Example}} (collected specimen)

{{pagelink:ServiceRequest-WGSTestOrderFormUpdated-TrioTesting-Example}} (update to SR to link consent/specimen)

{{pagelink:Provenance-WGSTestOrderForm-TrioTestingProbandFather-Example}} (Provenance to track reason for change to SR, note: incorrect reference to Fetal Scenario SR, though structure remains the same)

POST of {{pagelink:Task-WGSRareDiseaseTestOrderAccepted-TrioTestingProband-Example}}

### 4. Lab forwards test request/ ROD/ samples to GEL/NGIS.

Change of owner on Task to GEL.

### 5. Requester checks current status of test request

GET /Task(s) with focus ServiceRequest for status of each task (e.g. Sample Sequencing, Interpretation etc.), subsequent call for /AuditEvent(s) with entity.what=Task for history of updates to tasks if needed (e.g. accepted, in-progress, completed)

### 6. Requester views final report on patient

Task marked as completed: {{pagelink:Task-WGSRareDiseaseTestOrderCompleted-TrioTestingProband-Example}}

DiagnosticReport, referenced from Task: 
{{pagelink:DiagnosticReport-PhoebeSmithGeneticReport-Example}}
