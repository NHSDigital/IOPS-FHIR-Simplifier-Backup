## {{page-title}}

The National Genomic Medicine Service is currently delivered through seven regional GLHs. The GLHs are responsible for coordinating services for their region. Currently, all tests are routed via the Home GLH from any requester (primary, secondary, or tertiary care) within the region. For some specialist tests, a requester may directly send the test request and the sample directly to the specialist lab. R14 (as  test directory version 5.2, June 2023) is one such example. The requester will create and submit the test request and sample. The receiving lab (Exeter) will be immediately notified of the test request via messaging.

The sample may be received later (transport to Exeter) and will be reflected in the messaging as test received, awaiting sample. Confirmation is required from the GMS on if the Home GLH (i.e., the region in which the request was made, should be notified as cc from a monitoring perspective). 

The introduction of a central service will support the routing of tests to the given lab defined within the routing tables. In the event no rule exists, the test request will be defaulted to the Home GLH. 

### [Link to the High Fidelity Wireframe for the Direct to Lab Scenario](https://rgvu8f.axshare.com/)

The following steps is a walk through of:

### 1. Requester searches for a patient (a dummy patient has been pre-populated as an example)

**Params:**
```
given=James
family=Meltcalfe
birthdate=eq2013-10-10
```

**Response:**

{{pagelink:Patient-JamesMetcalfe-Example}}

### 2. Requester searches for appropriate code  (R14- test routes directly to Exeter)

Call to Digital Test Directory (out of scope for GMS central broker)

### 3. Requester completes the test order form and submits the request and indicates that ROD will follow

Transaction Bundle consisting of:

{{pagelink:Patient-JamesMetcalfe-Example}}

{{pagelink:Observation-DiseasePenetrance-Example}}

{{pagelink:Observation-Immunodefficiency-Example}}

{{pagelink:PractitionerRole-EugeneSmith-Example}}

{{pagelink:ServiceRequest-WGSTestOrderForm-DirectToLab-Example}}

### 4. Requester indicates that sample is going to be collected at a later date

Indicated through absence of Specimen resource in message or absence of ```Specimen.collectedDateTime```/```Specimen.status=unavailable```

### The lab (exeter) recieves the test request and:

### 1. Views the completed test order form

Obtained through GET /ServiceRequest or /GET Task requests (using params on {{pagelink:Home/FHIRAssets/CapabilityStatements}} to filter results) for non-routed requests. (Dashboard of available requests)

OR

Obtained through GET /Task request (filtered by GLH owner) for routed requests.

Then

GET /Task by Id and referenced ServiceRequest for view of individual.

### 2. Triages the test request as Awaiting further information (sample/ROD)

POST of {{pagelink:Task-WGSRareDiseaseTestOrderHold-DirectToLab-Example}}


### 1. Requesting Team completes Record of Discussion

POST of Consent, RoD and update to ServiceRequest to add supportingInfo link:

(note examples reference incorrect patient but structure remains the same)

{{pagelink:Consent-RoDYoungPersonAssentFormAvailable-Example}}

{{pagelink:QuestionnaireResponse-RoD-PheobeSmithamYPAForm-Example}}

{{pagelink:ServiceRequest-WGSTestOrderFormUpdated-DirectToLab-Example}}

{{pagelink:Provenance-WGSTestOrderForm-DirectToLab-Example}}

### 2. Lab recieves sample/ROD

POST of Specimen resources and GET from Lab 

{{pagelink:Specimen-JamesMetcalfeBloodEDTA-Example}}

### 3. Accepts the test request once sample is aligned with the test request at the lab

POST of {{pagelink:Task-WGSRareDiseaseTestOrderAccepted-DirectToLab-Example}}


### 1. Requester view status of test (complete)

GET /Task(s) with focus ServiceRequest for status of each task (e.g. Sample Sequencing, Interpretation etc.), subsequent call for /AuditEvent(s) with entity.what=Task for history of updates to tasks if needed (e.g. accepted, in-progress, completed)

### 2. Requester access PDF Report

The report will be linked as an output to the associated Task:

{{pagelink:Task-WGSRareDiseaseTestOrderCompleted-DirectToLab-Example}}

For unstructured reports, minimal metadata is required in the DiagnosticReport resource:

{{pagelink:DiagnosticReport-JamesMetcalfeGeneticReport-Example}}