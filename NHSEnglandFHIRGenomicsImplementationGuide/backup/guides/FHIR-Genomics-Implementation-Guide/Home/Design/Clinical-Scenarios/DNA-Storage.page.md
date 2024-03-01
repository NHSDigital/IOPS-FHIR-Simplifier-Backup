## {{page-title}}

DNA Storage (R346, R373, R332, R374) may be requested where genomic testing is likely required in the future, but further information or discussion is required prior to making the test request. In this scenario, DNA may be stored for future genomic testing or to help with testing of other family members.

The requester will create a test request electronically (e.g., R346 1) and record the reason for testing as “Stored DNA”, with the option to record the storage location (if known). The lab receives the test request in real time and samples (at a later date) and follows the current procedure for DNA storage. The requester can then indicate any subsequent electronic test requests the use of stored DNA (sample type). There would be no need to collect a new sample from the patient and the lab will activate the testing in the laboratory systems (LIMS).

**Note:** DNA storage depends on the quality/amount of DNA originally obtained and banked samples maybe used for multiple tests over multiple years.

### [Link to the High Fidelity Wireframe for the DNA Storage Scenario](https://p2o81u.axshare.com/)

The following steps is a walk through of:

### 1. Requester searches for a patient (a dummy patient has been pre-populated as an example)

**Params:**
```
given=Tim 
family=Mclullichs
birthdate=eq1954-10-29
```

**Response:**

{{pagelink:Patient-TimMclullichs-Example}}

### 2. Requester selects code appropriate Test directory code for storage of material (R346, R373, R332, R374)

Saved against ServiceRequest.code

### 3. Requester completes test order form

POST of test order bundle with {{pagelink:ServiceRequest-TestOrderForm-StorageOfMaterial-Example}}

### 4. Requester indicates that sample is going to be collected at a later date

Indicated through absence of Specimen resource in message or absence of ```Specimen.collectedDateTime```/```Specimen.status=unavailable```

### The lab recieves the test request and:

### 1. Views the completed test order form

Obtained through GET /ServiceRequest or /GET Task requests (using params on {{pagelink:Home/FHIRAssets/CapabilityStatements}} to filter results) for non-routed requests. (Dashboard of available requests)

OR

Obtained through GET /Task request (filtered by GLH owner) for routed requests.

Then

GET /Task by Id and referenced ServiceRequest for view of individual.

### 2. Accepts the test request and indicates the material is to be stored

POST of {{pagelink:Task-TestOrderFormAccepted-StorageOfMaterial-Example}}

### 3. Lab completes test request once material is stored

Marking of Task as completed


### 1. Requester contacts the lab to confirm material avaialble and can be used for new test

Outside Genomic Order Management Comms

### 2. Requester creates new test request and indicates use of existing sample in storage (sample collected at later date)

POST of test order bundle with {{pagelink:ServiceRequest-NonWGSTestOrderForm-UsingStoredSample-Example}}

### 3. Lab recieves test request, accepts test request once sample and request are aligned

POST of {{pagelink:Task-NonWGSTestOrderFormAccepted-UsingStoredSample-Example}}