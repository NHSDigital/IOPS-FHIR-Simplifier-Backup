## {{page-title}}

The National Genomic Test Directory defines the testing criteria for reanalysis as genomic data which has previously been interpreted and reported and is required due to:

- New clinical information or clinical events which would substantially change the relevant genomic target OR
- Sufficient time has passed since the initial analysis that new gene discovery will have substantially increased the relevant genomic target OR
- A technical or scientific advance requires reanalysis of a group of test to detect an important new source of actionable diagnoses. 

The requirement for electronic test ordering is to consider reanalysis as a new test request (Non-WGS and WGS), in addition to the original test request, where there is no sample allocated. The new test will be based on existing sequenced data resulting in the generation of new report once the data has been re-analysed. There is a requirement to indicate the original test directory code for which reanalysis is being actioned upon as part of the electronic test request ordered and capture additional information as part of the test request.

For further details, refer to [Reanalysis of genomic sequencing data for rare disease patients](https://future.nhs.uk/connect.ti/NHSgenomics/view?objectId=154355365).

### Reinterpretation/ Reanalysis Impact on WGS (NGIS- current challenge) 

NGIS’s interpretation portal can only hold one single version of the analysis. This means that if a WGS test request is generated on the patient, the single current version of the analysis is held. If there is a need for secondary analysis and a subsequent test is requested, the data previously held in the interpretation portal is overwritten. The problem of overwriting the primary analysis of the original data has been raised as a clinical safety risk and is being progressed with NGIS and will remain the responsibility of NGIS to address. 

From a requirements standpoint, the requester should have the ability to create a request for secondary analysis. The GLH will submit the request to NGIS in a business-as-usual capacity. 

### [Link to the High Fidelity Wireframe for the Re-analysis Scenario](https://atiyuk.axshare.com/)

### Requester:

#### 1. Requester to create a new test request for reanlaysis
#### 2. Requester to indicate no sample required

**POST transaction Bundle to GMS baseURL:**

{{pagelink:Bundle-NonWGSTestOrderForm-Reanalysis-Example}}

No Sample Required indicated through test code and note on ServiceRequest.

**Response:**

OperationOutcome with appropriate success/failure codes: {{pagelink:OperationOutcome-SuccessfulValidation-Example}}

### Lab:

#### 1. Recieve the test request for reanalysis

Obtained through GET /ServiceRequest or /GET Task requests (using params on {{pagelink:Home/FHIRAssets/CapabilityStatements}} to filter results) for non-routed requests. (Dashboard of available requests)

OR

Obtained through GET /Task request (filtered by GLH owner) for routed requests.

Then

GET /Task by Id and referenced ServiceRequest for view of individual.

#### 2. Accept test request for re-analysis

POST of {{pagelink:Task-NonWGSRareDiseaseTestOrderAccepted-Reanalysis-Example}}

### Requester:

#### 1. Requester to view current status of Test Request

GET /Task(s) with focus ServiceRequest for status of each task (e.g. Sample Sequencing, Interpretation etc.), subsequent call for /AuditEvent(s) with entity.what=Task for history of updates to tasks if needed (e.g. accepted, in-progress, completed)