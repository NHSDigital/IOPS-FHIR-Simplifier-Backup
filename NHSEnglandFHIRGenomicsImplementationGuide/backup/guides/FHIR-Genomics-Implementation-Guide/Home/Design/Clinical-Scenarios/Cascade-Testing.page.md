## {{page-title}}

Cascade testing may be defined as the positive result of a singleton test triggering the need for family members to be tested by a requester. For example, in the instance of Familial Hypercholesterolaemia (R134), a positive result of the test will guide the management for the patient and their family members. 

Cascade Testing is recorded on a rare disease test request order as the “Reason for Testing- Carrier or Predictive/ Pre-symptomatic.” Each cascade test is treated as a new test request and will be sent to the GLH with a sample(s). 

### [Link to the High Fidelity Wireframe for the Cascade Testing](https://ytlqh0.axshare.com/)

The following steps is a walk through of:

### 1. Requester (Specialist Nurse) searches for a patient (a dummy patient has been pre-populated as an example)

**Params:**
```
given=Fay
family=Mutlow
birthdate=eq1990-06-01
```

**Response:**

{{pagelink:Patient-FayMutlow-Example}}

### 2. Requester (Specialist Nurse) searches for appropriate description/code (For e.g. FH is used in this scenario)

ServiceRequest.code=R134

### 3. Requester (Specialist Nurse) completes the Non WGS Rare Disease Test Order Form. In this example, a family member is being tested due to a positive result.

POST of {{pagelink:ServiceRequest-NonWGSTestOrderForm-CascadeTesting-Example}}

Linked to previous ServiceRequest through ServiceRequest.basedOn to indicate this is a cascade test.

### 4. Requester (Specialist Nurse) submits test order and indicates that sample is to be collected at a later date

Post of transaction Bundle consisting of the following resources:

{{pagelink:Patient-FayMutlow-Example}}

{{pagelink:ServiceRequest-NonWGSTestOrderForm-CascadeTesting-Example}}

{{pagelink:Observation-DutchLipidScore-Example}}

{{pagelink:Observation-QueryXanthoma-Example}}

{{pagelink:Observation-SimonBroomeCriteria-Example}}

{{pagelink:PractitionerRole-LoisLane-Example}}

{{pagelink:PractitionerRole-MarySmith-Example}}

{{pagelink:Specimen-BloodEDTA-WithCollectoinDetails-Example}}

### The lab recieves the test request and:

### 1. Views the completed test order form

Obtained through GET /ServiceRequest or /GET Task requests (using params on {{pagelink:Home/FHIRAssets/CapabilityStatements}} to filter results) for non-routed requests. (Dashboard of available requests)

OR

Obtained through GET /Task request (filtered by GLH owner) for routed requests.

Then

GET /Task by Id and referenced ServiceRequest for view of individual.

### 2. Modifies the test request with the appropriate additional information and accepts the test request

POST of {{pagelink:ServiceRequest-SavedTestOrderUpdated-CascadeTesting-Example}}

(and Provenance resource to indicate reason for change)

### 3. Once analysis is complete, the lab issues the final report to the requester

POST of {{pagelink:Task-NonWGSRareDiseaseTestOrderCompleted-CascadeTesting-Example}} with reference to report resource

### The requester:

### 1. Views the current status of the test and accesses the final report.

GET of linked DiagnosticReport: {{pagelink:DiagnosticReport-FayMutlowGeneticReport-Example}}