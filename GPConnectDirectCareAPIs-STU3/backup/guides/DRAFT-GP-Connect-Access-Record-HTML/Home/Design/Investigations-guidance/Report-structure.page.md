## {{page-title}}

The following entity diagram describes the logical model for investigations in GP Connect:

{{ render: Pathology_Logical_Model.png }}

In the image we have made the key entities more prominent. Entities representing organizations and practitioners sit in the background but are still part of the exported data.

|Entity Name|Description|
|---|---|
|Test Report|The summary data from the test report including the clinical interpretation|
|Test Group|Output from a group of tests including the clinical interpretation|
|Test Result|Output from a single test including the clinical interpretation|
|Specimen|Information on the specimen tested|
|Test Report Filing|Information recorded by the general practice clinician when they file the test report|
|Test Request Summary|A summary of the original test request that is returned with the test report|
|Test Report Document|The test report in the format it was received by the GP practice|
|Test Result Document|Documents that form part of the test results (for example, images and charts)|

The ‘Test Report Document’ and ‘Test Result Document’ are out of scope for the current iteration, but are represented in the diagram.

We have modelled the investigations report in such a way that it will be able to support any data that is currently sent in the EDIFACT message and also leaves room to send further data items as and when providing systems are able to support them. The model is also intended to be flexible enough to support the many different patterns and types of result that can be sent so it can be easily adapted to support other test results stored in the GP system.

### Available FHIR resources

There are a number of resources available in FHIR to represent the different entities that exist in investigation reporting. The resources that we are concerned with in order to represent our model are in the following table.

|Resource name|Description|
|---|---|
|[`ProcedureRequest`](https://simplifier.net/guide/gpconnect-data-model/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-GPC-ProcedureRequest-1?version=current)|For requesting investigations to be performed by a laboratory|
|[`DiagnosticReport`](https://simplifier.net/guide/gpconnect-data-model/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-GPC-DiagnosticReport-1?version=current)|A reporting structure that contains results and any relevant data such as specimen details or attribution|
|[`Specimen`](https://simplifier.net/guide/gpconnect-data-model/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-GPC-Specimen-1?version=current)|For carrying details about the specimen that was collected and the investigations were performed on|
|[`Observation`](https://simplifier.net/guide/gpconnect-data-model/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-GPC-Observation-1?version=current)|Represents details related to the test group header, test result and details of when a report or group of results was filed into the patient record|

There are other resources that may be relevant in the future, such as imagingStudy, imagingManifest and sequence, but currently we are only utilising the resources listed in the table.

### Using the FHIR profiles to represent the logical model

We have mapped these resources on to the logical model in the diagram below:

{{ render: Pathology_Logical_Model_with_FHIR_resource_names.png }}

DiagnosticReport is at the centre of the model and all the other entities are linked to from there.

The `Observation` resource is used for three different entities within the model. The test group header, test results and to contain any filing comments. Although we have used this resource in different settings, there will be only one FHIR profile that can then be populated appropriately for each individual use.

There are detailed notes about how to populate each of these resources in the individual resource pages.

---