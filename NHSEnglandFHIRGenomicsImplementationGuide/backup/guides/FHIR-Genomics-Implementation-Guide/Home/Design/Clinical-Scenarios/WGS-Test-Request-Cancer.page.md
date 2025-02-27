## {{page-title}}

The Cancer test order process is equivalent for WGS and Non-WGS tests.
For WGS, it is expected the `Process Genomic Test Request` Task would be routed to GEL to allow raising of the request in NGIS. The ServiceRequest.category would indicate the test is a 'cancer-wgs' test as with the WGS Rare Disease scenario.

All WGS tests are expected to include a RoD form: {{pagelink:Questionnaire-Genomic-Testing}}

For the WGS Tumour First, Germline Later use case, it is expected requesters would submit an additional ServiceRequest for the Germline Later test, using ServiceRequest.basedOn to reference the initial Tumour First test.

### [Link to the High Fidelity Wireframe for the WGS Cancer Test Order Form](https://4r1u14.axshare.com/?id=8k29q1&p=wgs_cancer_test_order&g=1)

## Examples for Solid Tumour Test

{{pagelink:ServiceRequest-WGSTestOrderForm-CancerSolidTumor-Example}}

{{pagelink:Specimen-SolidTumorDemeizaSeo-Example}}

{{pagelink:Observation-TumourTypeDemeizaSeo-Example}}

{{pagelink:Observation-PercentageMalignantNuclei-Example}}

{{pagelink:BodyStructure-BodySiteLocationAbdomen-Example}}

This would result in a set of Tasks for processing of the order, e.g.:

{{pagelink:Task-WGSCancerTestOrder-SolidTumor-Example}}

## Examples for HeamOnc Test (Tumour First - Germline Late)

### 1. Tumour First request

For the Tumour First - Germline Late scenario, the Tumour First test request is first created:

{{pagelink:ServiceRequest-WGSTestOrderForm-CancerHaemOnc-Example}}

{{pagelink:Specimen-PatrickSammyBoneMarrowAspiration-Example}}

{{pagelink:Observation-PatrickSammyNoBoneMarrowTransplant-Example}}

{{pagelink:Observation-NucleatedCellCountWGSSample-Example}}

{{pagelink:Observation-BlastPercentageWGSSample-Example}}

{{pagelink:Condition-AcuteMyeloidLeukaemia-Example}}

### 2. Germline Late Request

Next, a new request for the Germline sample is created, based on the previous Tumour First request:

{{pagelink:ServiceRequest-WGSTestOrderForm-GermlineLate-Example}}

{{pagelink:Specimen-PatrickSammyBloodEDTA-Example}}

### 3. Task Management

Tasks for each ServiceRequest will be created independently, it is up to client systems to link the 2 requests and progress tasks across the 2 requests.

{{pagelink:Task-WGSCancerTestOrder-HaemOnc-Example}}