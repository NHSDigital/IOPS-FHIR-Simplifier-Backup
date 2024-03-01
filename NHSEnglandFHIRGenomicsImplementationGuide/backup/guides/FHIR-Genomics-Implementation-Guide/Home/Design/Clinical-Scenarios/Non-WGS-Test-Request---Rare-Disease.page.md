## {{page-title}}

The National Genomics Test Directory specifies available tests and eligibility criteria. Testing within genomics goes beyond cradle to grave. Genomic testing may occur on fetuses, patients who are alive, their family members or patients who are deceased. Any electronic test ordering system SHALL have the ability to communicate with the national Patient Demographic Service (PDS), provide the ability to place test requests for both patients who are alive or deceased and enable the receipt of the test request by the laboratory. 

A new test request may be accompanied with a request for samples. Once collected the sample and test request are sent to the Home GLH for processing. The requirement is when an electronic test request is submitted by the requester, the GLH will be notified in real time of the test request. As the sample may be collected later, the requirement is that the lab involved in collecting the sample provide an update of the sample sent and once the sample arrives at the GLH, the status of sample received is provided. 

The following steps is a walk through of a Non-WGS Test order workflow:

### [Link to the High Fidelity Wireframe for the Non WGS Rare Disease Test Scenario](https://9yv5b6.axshare.com/)

### 1. Requester searching for a patient (a dummy patient has been pre-populated as an example) - Via PDS GET /Patient request

**Params:**
```
given=Meir
family=Lieberman
birthdate=eq2005-12-19
```

**Response:**

{{pagelink:Patient-MeirLiebermanPDS-Example}}

### 2. Requester selects a Non WGS Rare Disease Test Order Form - UI Only

Represented in ServiceRequest via ServiceRequest.category:
```
{
    "system":"https://fhir.hl7.org.uk/CodeSystem/UKCore-GenomeSequencingCategory",
    "value":"rare-disease-non-wgs",
    "display":"Rare Disease - Non-WGS"
}
```

### 3. Requester completes the Non WGS Rare Disease Test Order Form and submits the request - 

**POST transaction Bundle to GMS baseURL:**

{{pagelink:Bundle-NonWGSTestOrderForm-Example}}

**Response:**

OperationOutcome with appropriate success/failure codes: {{pagelink:OperationOutcome-SuccessfulValidation-Example}}

### 4. Requester indicates that sample is going to be collected at a later date

Indicated through absence of Specimen resource in message or absence of ```Specimen.collectedDateTime```/```Specimen.status=unavailable```

### The lab receives the test request and:

#### 1. Views the completed test order form

Obtained through GET /ServiceRequest or /GET Task requests (using params on {{pagelink:Home/FHIRAssets/CapabilityStatements}} to filter results) for non-routed requests. (Dashboard of available requests)

OR

Obtained through GET /Task request (filtered by GLH owner) for routed requests.

Then

GET /Task by Id and referenced ServiceRequest for view of individual.

#### 2. Accepts the test request

POST of {{pagelink:Task-NonWGSRareDiseaseTestOrderAccepted-Example}}

OR

#### 3. Rejects the test request 

POST of {{pagelink:Task-NonWGSRareDiseaseTestOrderRejected-Example}}

OR

#### 4. Modifies the test request

POST of {{pagelink:ServiceRequest-SavedTestOrderUpdated-Example}}

### View of Status History

GET /Task(s) with focus ServiceRequest for status of each task (e.g. Sample Sequencing, Interpretation etc.), subsequent call for /AuditEvent(s) with entity.what=Task for history of updates to tasks if needed (e.g. accepted, in-progress, completed)