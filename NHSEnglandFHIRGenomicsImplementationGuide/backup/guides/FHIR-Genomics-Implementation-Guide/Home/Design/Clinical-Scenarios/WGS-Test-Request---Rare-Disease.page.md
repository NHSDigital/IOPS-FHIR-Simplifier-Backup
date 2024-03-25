## {{page-title}}

For each individual WGS Test Request ordered (includes duos/trios/larger family groups), an accompanying Record of Discussion (RoD) is a mandatory requirement to progress with the test request. NGIS requires both the completion of the test request, associated sample, and the RoD, which is first routed to the appropriate Home GLH. Currently, WGS Test Requests are manually transcribed onto an electronic form within NGIS by the GLH. Rollout of direct clinician access to NGIS remains limited. 

In the future state, the electronic test request, sample, and RoD (electronic or pdf attachment) will be completed by members of the requesting team. Information may be completed at different stages and the GLH may receive the WGS test request, the sample, and the RoD at different times. The requirement is to remove the double entry of the test order and RoD into NGIS and provide the GLH with the ability to forward on all order components electronically to NGIS. The central service will indicate when each component (Test order, sample, and RoD) has been received by the GLH and once all components have been forwarded onto to GEL. 

For further details on WGS Test Requesting and RoD, refer to WGS Resources and Genomics England.

The following steps is a walk through of a WGS Test order workflow:

### [Link to the High Fidelity Wireframe for the WGS Rare Disease Test Scenario](https://tenq2a.axshare.com/)

### 1. Requester searching for a patient (a dummy patient has been pre-populated as an example) - Via PDS GET /Patient request

**Params:**
```
given=Lindsay
family=Sorrell
birthdate=eq2011-04-12
```

**Response:**

{{pagelink:Patient-LindsaySorrellPDS-Example}}

### 2. Requester selects a WGS Rare Disease Test Order Form - UI Only

Represented in ServiceRequest via ServiceRequest.category:
```
{
    "system":"https://fhir.hl7.org.uk/CodeSystem/UKCore-GenomeSequencingCategory",
    "value":"rare-disease-wgs",
    "display":"Rare Disease - WGS"
}
```

### 3. Requester completes the WGS Rare Disease Test Order Form and submits the request - 

**POST transaction Bundle to GMS baseURL:**

{{pagelink:Bundle-WGSTestOrderForm-Example}}

**Response:**

OperationOutcome with appropriate success/failure codes: {{pagelink:OperationOutcome-SuccessfulValidation-Example}}

### 4. Requester indicates that sample is going to be collected at a later date

Indicated through absence of Specimen resource in message or absence of ```Specimen.collectedDateTime```/```Specimen.status=unavailable```

### 5. Requester indicates that Record of Discussion is going to be collected at a later date

Indicated through absence of QuestionnaireResponse resource in message with ```QuestionnaireResponse.questionnaire:"https://fhir.nhs.uk/Questionnaire/NHSDigital-Questionnaire-Genomics-Example"``` or ```Consent.status:"proposed"```

### The lab receives the test request and:

#### 1. Views the completed test order form

Obtained through GET /ServiceRequest or /GET Task requests (using params on {{pagelink:Home/FHIRAssets/CapabilityStatements}} to filter results) for non-routed requests. (Dashboard of available requests)

OR

Obtained through GET /Task request (filtered by GLH owner) for routed requests.

Then

GET /Task by Id and referenced ServiceRequest for view of individual.

#### 2. Places the test request as awaiting further information - Record of Discussion

POST of {{pagelink:Task-WGSRareDiseaseTestOrderAccepted-Example}}

#### 3. The lab receives the Record of Discussion, Sample and changes status from Awaiting Further Information to Accepted

POST of {{pagelink:Bundle-WGSRoD-Example}} and subsequent marking of Task as accepted by Lab

#### 4. The lab reviews the completed WGS Test Order Form, Sample and Record of Discussion and forwards the components to NGIS 

POST of {{pagelink:Task-WGSRareDiseaseTestOrderForwarded-Example}}

### View of Status History

GET /Task(s) with focus ServiceRequest for status of each task (e.g. Sample Sequencing, Interpretation etc.), subsequent call for /AuditEvent(s) with entity.what=Task for history of updates to tasks if needed (e.g. accepted, in-progress, completed)