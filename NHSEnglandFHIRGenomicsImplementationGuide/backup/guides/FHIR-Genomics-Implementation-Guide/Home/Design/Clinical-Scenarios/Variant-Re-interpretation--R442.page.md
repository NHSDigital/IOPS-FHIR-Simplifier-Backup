## {{page-title}}

The testing criteria for Variant Re-interpretation is defined in the National Genomic Test Directory as the requirement for an interpretation of a known variant to determine if the pathogenic status has changed since primary analysis and reporting or a previous re-interpretation. Re-interpretation of a variant may be performed due to:

- A request from a clinician responsible for a patient with a report variant of uncertain significance, OR
- New evidence available that will likely change the classification of a variant. For example, the identification of additional patient(s) with the same genetic variant or new functional evidence, 
AND
- Where either, there is new clinical information related to the patient or their family, or sufficient time has passed that there may be additional published evidence or knowledge, that could result in a change to the classification of the variant. 

Variant Re-interpretation SHALL be treated as a new test request (WGS and Non-WGS) where there is no sample allocated, based on re-interpretation of existing sequenced data and the generation of a new report once re-interpretation is complete. Existing or old data SHALL NOT be lost or overwritten in the event a new there is a new re-interpretation request. 

### [Link to the High Fidelity Wireframe for the Variant Re-interpretation Scenario](https://kljmrk.axshare.com/)

The following steps is a walk through of:

### 1. Requester searches for a patient (a dummy patient has been pre-populated as an example)

**Params:**
```
given=Salima
family=Pomfrets
birthdate=eq1993-11-27
```

**Response:**

{{pagelink:Patient-SalimaPomfrets-Example}}

### 2. Requester searches for approrpriate test directory code R442- Variant Re-interpretation

Call to Digital Test Directory (out of scope for GMS central broker)

### 3. Requester completes the electronic form and submits the request

POST of {{pagelink:ServiceRequest-NonWGSTestOrder-VariantReinterpretation-Example}}

Note: Supporting info can be optionally obtained from data related to the previous ServiceRequest (linked from ServiceRequest.basedOn), if unchanged.

### 4. Requester indicates that no sample is required.

Indicated through absence of Specimen resource in message or absence of ```Specimen.collectedDateTime```/```Specimen.status=unavailable```

### The lab recieves the test request and:

### 1. Views the completed test order form

Obtained through GET /ServiceRequest or /GET Task requests (using params on {{pagelink:Home/FHIRAssets/CapabilityStatements}} to filter results) for non-routed requests. (Dashboard of available requests)

OR

Obtained through GET /Task request (filtered by GLH owner) for routed requests.

Then

GET /Task by Id and referenced ServiceRequest for view of individual.

### 2. Accepts the test request

POST of {{pagelink:Task-NonWGSTestOrderAccepted-VariantReinterpretation-Example}}