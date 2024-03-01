## {{page-title}}

In certain circumstances, genomic tests may be sent to a laboratory team outside of the UK for further analysis. One such example of a test is Oncotype DX (M3.2). Oncotype DX is currently dispatched out of the UK by courier to Genomic Health in the U.S. Currently, the oncologist partially completes the tissue requisition form prior to sending the form to the cell path department, where the requisition is married up with the breast cancer tissue block and tumour information prior to dispatching by courier to the U.S. In another scenario, (M2.5- genomic instability testing for ovarian cancer by Myriad), the local lab will collect and send the tissue to the GLH. The GLH will forward on the request and the sample and dispatch by courier to the US.
 
In both instances, a new test request is created and the sample along with the test request is forwarded by the Home GLH to any out of country partners. 

### [Link to the High Fidelity Wireframe for the Out of Country Scenario](https://u9whst.axshare.com/)

The following steps is a walk through of:

### 1. Requester searches for a patient (a dummy patient has been pre-populated as an example)

**Params:**
```
given=Kay
family=Burbridge
birthdate=eq1983-06-02
```

**Response:**

{{pagelink:Patient-KayBurbridge-Example}}


### 2. Requester searches for Test code (for e.g. M3.2)

Call to Digital Test Directory (outside scope for GMS central broker)

### 3. Requester completes the test order form and submit requests to lab

POST of transaction Bundle consisting of the following resources:

{{pagelink:BodyStructure-SpecimenBodySiteLocation-Example}}

{{pagelink:Condition-BreastCancer-Example}}

{{pagelink:Observation-NecrosisKayBurbridge-Example}}

{{pagelink:Observation-CellularityKayBurbridge-Example}}

{{pagelink:Observation-NeoplasticCellKayBurbridge-Example}}

{{pagelink:Observation-TumourTypeKayBurbridge-Example}}

{{pagelink:Patient-KayBurbridge-Example}}

{{pagelink:ServiceRequest-NonWGSTestOrderForm-OutOfCountry-Example}}

{{pagelink:Specimen-TissueResection-Example}}

### The lab recieves the test request and:

### 1. Views the completed test order form

Obtained through GET /ServiceRequest or /GET Task requests (using params on {{pagelink:Home/FHIRAssets/CapabilityStatements}} to filter results) for non-routed requests. (Dashboard of available requests)

OR

Obtained through GET /Task request (filtered by GLH owner) for routed requests.

Then

GET /Task by Id and referenced ServiceRequest for view of individual.

### 2. Accepts the test request

POST of Task with status=accepted

### 3. Lab indicates in LIMS that request is to be sent abroad (For e.g. Genomic Health- U.S.A)

POST of {{pagelink:Task-NonWGSRareDiseaseTestOrderForwarded-OutOfCountry-Example}}

Note: in cases where the responsible owner of a Task is not capbable of providing status updates to the broker, it is the responsibility of the referring organization to provide updates on the owners behalf and reallocate Tasks once ownership changes.