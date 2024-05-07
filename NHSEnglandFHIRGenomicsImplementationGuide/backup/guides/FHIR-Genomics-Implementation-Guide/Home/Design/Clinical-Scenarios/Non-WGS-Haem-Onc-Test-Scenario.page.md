## {{page-title}}

The Cancer test order process is equivalent for WGS and Non-WGS tests.
For WGS, it is expected Tasks would be routed to GEL (or have GEL indicated as the performer on the ServiceRequest) and the ServiceRequest.category would indicate the test is a 'cancer-wgs' test as with the WGS Rare Disease scenario.
All WGS tests are expected to include a RoD form: {{pagelink:Questionnaire-Genomic-Testing}}

For the WGS Tumour First, Germline Later use case, it is expected requesters would submit an additional ServiceRequest for the Germline Later test, using ServiceRequest.basedOn to reference the initial Tumour First test.

### [Link to the High Fidelity Wireframe for the Non WGS Haem-Onc Test Scenario](https://uj5cen.axshare.com/)

The following steps is a walk through of:

### 1. Local SIHMDS consultant to search for a patient (a dummy patient has been pre-populated as an example)

**Params:**
```
given=Patrick
family=Sammy
birthdate=eq1982-10-06
```

**Response:**

{{pagelink:Patient-PatrickSammy-Example}}

### 2. SIHMDS consultant selects a Non WGS Haem Onc Test Order Form

Represented in ServiceRequest via ServiceRequest.category:
```
{
    "system":"https://fhir.hl7.org.uk/CodeSystem/UKCore-GenomeSequencingCategory",
    "value":"cancer-non-wgs",
    "display":"Cancer - Non-WGS"
}
```

### 3. SIHMDS consultant completes the Non WGS Haem Onc Test Order Form and submits the request

**POST transaction Bundle to GMS baseURL:**

Bundle consists of:

{{pagelink:ServiceRequest-NonWGSTestOrderForm-HaemOncology-Example}}

{{pagelink:PractitionerRole-HazelSmithPathology-Example}}

{{pagelink:Observation-WhiteBloodCell-Example}}

{{pagelink:Observation-Platelets-Example}}

{{pagelink:Observation-Neutrophils-Example}}

{{pagelink:Observation-Haemoglobin-Example}}

{{pagelink:Observation-Bruising-Example}}

{{pagelink:Condition-Hepatosplenomegaly-Example}}

**Response:**

OperationOutcome with appropriate success/failure codes: {{pagelink:OperationOutcome-SuccessfulValidation-Example}}

### 4. SIHMDS consultant enters sample details

**Post of Specimen and associated resources (can be part of initial test order bundle if known at time of order submission)**

{{pagelink:Specimen-BoneMarrowAspiration-Example}}

{{pagelink:Observation-BlastPercentage-Example}}

{{pagelink:Observation-NucleatedCellCount-Example}}

### The GLH lab recieves the test request

### 1. Views the completed test order form

Obtained through GET /ServiceRequest or /GET Task requests (using params on {{pagelink:Home/FHIRAssets/CapabilityStatements}} to filter results) for non-routed requests. (Dashboard of available requests)

OR

Obtained through GET /Task request (filtered by GLH owner) for routed requests.

Then

GET /Task by Id and referenced ServiceRequest for view of individual.

### 2. Accepts the test request and proceeds with request

Updated ServiceRequest:
{{pagelink:ServiceRequest-NonWGSTestOrderForm-HaemOncologyUpdated-Example}}

POST of {{pagelink:Task-NonWGSRareDiseaseTestOrderAccepted-HaemOncology-Example}}

### SIHMDS Consultant

### 1.  View current status of test.

GET /Task(s) with focus ServiceRequest for status of each task (e.g. Sample Sequencing, Interpretation etc.), subsequent call for /AuditEvent(s) with entity.what=Task for history of updates to tasks if needed (e.g. accepted, in-progress, completed)

Note: the genomic laboratory is responsible for the generation of the genomic report. The creation of an integrated report is out of scope and will be managed as per current processes by the SIHMDS consultant