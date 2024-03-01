## {{page-title}}

The following test types may be requested as an additional or follow up test at the lab. In these instances, the lab acts as the originating requester and may add on additional tests to validate the pathway (these tests may or may not be on the National Genomics Test Directory).

- **Confirmatory Test (R443):** use of alternative test methods to confirm the conclusions of an original genomic test requested. 
- **Reflex Test:** is the next course of action (new test request) based on the outcome of the original genomic test requested and are related to the outcomes. These tests are internal to the laboratories. 
- **Lab Recommended Testing:** management of situations where the requester has placed a test request however, the lab has replaced the test with a better option or where the optimal test could not be delivered due to sample limitations. 
- **Re-test:** based on quality or a change in what the test provides (panels) and is treated as a new test.  
In these instances, existing samples on the patient may be used by the lab to perform additional testing. 
Note: Existing DNA/RNA, Cultures may be used for testing in the future for unrelated episodes of testing. 

### [Link to the High Fidelity Wireframe for the Non WGS Rare Disease Test Scenario](https://o719on.axshare.com/)

The following steps is a walk through of a follow up test type (e.g. Reflex Testing) for a patient:

### 1. Requester searches for a patient (a dummy patient has been pre-populated as an example)

**Params:**
```
given=Anita
family=Lamberts
birthdate=eq1993-11-14
```

**Response:**

{{pagelink:Patient-AnitaLambertsDeceasedPatient-Example}}

### 2. Requester searches for test directory code

Call to Digital Test Directory (outside scope for GMS central broker)

### 3. Requester completes test order form and submits request

POST of Test order transaction bundle including {{pagelink:ServiceRequest-NonWGSTestOrderForm-FollowupTest-Example}}

### 4. Requester indicates that sample is going to be collected at a later date

Indicated through absence of Specimen resource in message or absence of ```Specimen.collectedDateTime```/```Specimen.status=unavailable```

### The lab recieves the test request and:

### 1. Views the completed test order form

Obtained through GET /ServiceRequest or /GET Task requests (using params on {{pagelink:Home/FHIRAssets/CapabilityStatements}} to filter results) for non-routed requests. (Dashboard of available requests)

OR

Obtained through GET /Task request (filtered by GLH owner) for routed requests.

Then

GET /Task by Id and referenced ServiceRequest for view of individual.

### 2. Accepts the test request

POST of {{pagelink:Task-NonWGSRareDiseaseTestOrderAccepted-FollowupTest-Example}}

### 3. Lab indicates that further testing is required

This could be added as a note on the original ServiceRequest or Task which prompted further testing.

### 4. Lab requests a new test (reflex) to aid interpretation

Creation of new ServiceRequest through post of {{pagelink:ServiceRequest-NonWGSTestOrderForm-NewFollowupTest-Example}}

According to scenario, previous test is cancelled (indicated by POST of {{pagelink:Task-NonWGSRareDiseaseTestOrderCancelled-FollowupTest-Example}})

### 5. Lab issues report for patient

Tasks marked as completed {{pagelink:Task-NonWGSRareDiseaseTestOrderCompleted-FollowupTest-Example}}

### 6. Requester views status and final report

GET of linked DiagnosticReport {{pagelink:DiagnosticReport-AnitaLamberts-Example}}