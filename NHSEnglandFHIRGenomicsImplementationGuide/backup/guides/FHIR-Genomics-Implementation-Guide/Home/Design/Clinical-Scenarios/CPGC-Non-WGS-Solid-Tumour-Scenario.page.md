## {{page-title}}

The Cancer test order process is equivalent for WGS and Non-WGS tests.
For WGS, it is expected Tasks would be routed to GEL (or have GEL indicated as the performer on the ServiceRequest) and the ServiceRequest.category would indicate the test is a 'cancer-wgs' test as with the WGS Rare Disease scenario.
All WGS tests are expected to include a RoD form: {{pagelink:Questionnaire-Genomic-Testing}}

For the WGS Tumour First, Germline Later use case, it is expected requesters would submit an additional ServiceRequest for the Germline Later test, using ServiceRequest.basedOn to reference the initial Tumour First test.

### [Link to the High Fidelity Wireframe for the CPGC Non WGS Solid Tumour Scenario](https://wlajol.axshare.com/)

The following steps is a walk through of a Non WGS Solid Tumour Test Request. This scenario takes into considersation the set up CPGC's (location) as the initial point of triage and prep prior to forwarding the test request/sample to GLH.

### 1. Cellular Pathologist(Requester) to confirm Genomic Testing/ specimen block required.

Outside scope for central broker comms

### 2. Cellular Pathologist(Requester) to search for patient (a dummy patient has been pre-populated as an example) 

**Params:**
```
given=Zelma
family=Hadgkiss
birthdate=eq2011-03-19
```

**Response:**

{{pagelink:Patient-ZelmaHadjkiss-Example}}

### 3. Cellular Pathologist (Requester) to indicate appropriate Test directory code/description

Code M119 selected for ServiceRequest.code

### 4. Cellular Pathologist (Requester) to complete (as an example)- Non WGS Cancer (Solid Tumour) form and submit request with specimen details. Please note:specimen(s) may come from another lab in the region.

**POST transaction Bundle to GMS baseURL:**

{{pagelink:Bundle-NonWGSTestOrderForm-CancerSolidTumor-Example}}

**Response:**

OperationOutcome with appropriate success/failure codes: {{pagelink:OperationOutcome-SuccessfulValidation-Example}}

**Specimen details:**

{{pagelink:BodyStructure-BodySiteLocationLungs-Example}}

{{pagelink:Observation-Cellularity-Example}}

{{pagelink:Observation-Necrosis-Example}}

{{pagelink:Observation-NeoplasticCell-Example}}

{{pagelink:Observation-TumourType-Example}}

{{pagelink:Specimen-CancerSolidTumor-Example}}

{{pagelink:ServiceRequest-NonWGSTestOrderFormUpdated-SolidTumor-Example}}

### CPGC: (Set up to manage triage and prep for all solid tumors listed on the Test Directory)

### 1. Recieve test request electronically (* Note a CPGC may be in the same location as the GLH or at a different location) and specimen details

Obtained through GET /ServiceRequest or /GET Task requests (using params on {{pagelink:Home/FHIRAssets/CapabilityStatements}} to filter results) for non-routed requests. (Dashboard of available requests)

OR

Obtained through GET /Task request (filtered by GLH owner) for routed requests.

Then

GET /Task by Id and referenced ServiceRequest for view of individual.

### 2. Review/ Triage test request and specimen (when delivered to location)

GET of resources linked to ServiceRequest

### 3. Accept Test request and complete prep if specimen/test request meets criteria

PUT of {{pagelink:Task-NonWGSRareDiseaseTestOrderAccepted-SufficientSample-Example}}

Or

### 4. Set status to awaiting further information or Reject in the event criteria is not met

PUT of {{pagelink:Task-NonWGSRareDiseaseTestOrderRejected-CancerSolidTumor-Example}}

and {{pagelink:Home/Examples/Task/Task-NonWGSRareDiseaseTestOrder-InsufficientSample-Example.page.md}}

### 5. CPGC to forward (test request req details electronically) & sample to GLH once prep is complete to progress the request

PUT of {{pagelink:Task-NonWGSRareDiseaseTestOrderForwarded-SolidTumor-Example}}
