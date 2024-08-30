## {{page-title}}

Genomic tests can be categorised by clinical area (Haem/Onc, Neurology etc.), WGS vs. Non-WGS, whether the test is singleton/duo/trio and whether the test will be analysing/interpreting existing data. 

Clinical Area will be inferred through the CI/CITT code being requested.

WGS/non-WGS will be explicitly captured through ServiceRequest.category.

Singleton/Duo/Trio will be inferred through the number of ServiceRequests sent in a single transaction (grouped via requisition). This is still under discussion, if a single ServiceRequest is preferred, an extension to ServiceRequest to capture consultands may need to be developed.

Reanalysis/Reinterpretation will also be inferred through the CITT code being requested, though additional indicators are being investigated.

Reflex tests will be indicated through the ServiceRequest.intent = 'reflex-order'.

The indicative number of ServiceRequests, Samples and Reports required for each category are provided below:

|Type|No. Test Requests|No. Physical Samples|No. Test Reports|Notes|
|--|--|--|--|--|
|Singleton|1|1..* Proband|1||
|Duo|1|1..\* Proband, 1..\* Consultand 1|1||
|Trio|1|1..\* Proband, 1..\* Consultand 1, 1..\* Consultand 2|1||
|Re-analyse|1|0|1||
|Re-Interpret|1|0|1||
|Reflex/Confirmation|1..\*|1..\* Proband|1..\*||
|Diagnostic Support|1|1..\* Proband, 1..\* Relative|1|If the relative analysis identifies other important variants then they are referred into the Singleton pathway||

The Re-Analysis and Re-Interpret test types do not require samples as they are an instruction against an existing test request and data. In the test order system this will be represented by either linking the ServiceRequest to the previous ServiceRequest and/or by including the existing specimen reference in the new ServiceRequest.

For each of these test types the API calls and flow of resources will be the same, the difference will be the number of Patient, Specimen and other FHIR resources which are included and referenced from the ServiceRequest, Task and DiagnosticReport resource.

The following pages detail the different scenarios the interoperability solution is intended to support. Worked FHIR example resources for each scenario will be developed as work on the Alpha commences.

### No Sample Required 
In scenarios such as variant re-interpretation or re-analysis, there is no physical sample for the patient available. For these new test requests, the data is only used for re-interpretation or re-analysis of the original test ordered for the patient. Clear identification that there is no sample for the test request ordered is a requirement. Indication that a sample is not required is a crucial component in the overall sample tracking journey. 

### Sample collected now vs. at a later date  
When a new genomic test request is ordered, samples may either be collected at the point of the test being ordered or at a later date (e.g., patient booked into phlebotomy clinic for blood). There is an additional scenario where a sample from the patient may have been collected previously or there is no sample required for specific test types (re-analysis). As samples may be collected and sent across multiple organisational boundaries or within the organisation itself, the requirement is to ensure that samples are always associated with the correct test request ID and cater for scenarios where a sample is not required or has been stored previously. 
