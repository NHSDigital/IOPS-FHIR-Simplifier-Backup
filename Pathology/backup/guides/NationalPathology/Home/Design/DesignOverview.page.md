---
topic: DesignOverview
---
## Design Overview

Pathology data is used to support many aspects of patient care, including screening, diagnostic testing, treatment advice and the monitoring and management of conditions.

Although the focus of this release is on pathology test reporting, to provide wider context it is also useful to consider the test requesting process. The following describes a simplified, generic pathology test request and test report cycle (without any exception or alternative process flows):

- The Requesting Health Care Professional (HCP) determines that a patient requires a pathology test, for example to aid the diagnosis of a suspected condition or to monitor an existing condition.
- The Requesting HCP sends a test request to a designated pathology laboratory (typically based in a hospital trust).
- The patient provides a specimen. 
- The specimen is collected and sent to the laboratory.
- Upon receipt at the laboratory, the specimen is checked and matched with the test request. The details are recorded in the LIMS.
- The specimen is prepared, and the test(s) performed.
- The test report is generated and authorised for release.
- The test report is sent to the Requesting HCP.
- The test report is received by the Requesting HCP.
-The patient is informed of the test results and, if required, the Requesting HCP takes further action, for example, initiates a course of treatment, requests further tests or refers the patient to a specialist.

This process is illustrated in the following diagram:

{{render:PathologySimplifiedProcessFlow}}

There are many possible variations and exceptions to this basic process, including:

-	The type of Requesting Organisation (e.g. primary care, secondary care, community) and the role of the Requesting HCP.
-	The type of care that the patient is receiving e.g. in-patient, out-patient, community
-	Whether the test request is sent electronically or on paper.
-	The type and number of required tests.
-	The type and number of required specimens. Depending on the requested tests, a mix of specimen types may be required e.g. blood and urine. In a dynamic function test (e.g. a Glucose Tolerance Test) a series of samples are collected at defined time points before and after an intervention to assess the response to that intervention.
-	The organisation and HCP responsible for collecting the specimen and the location, timing and method of collection. In some cases, the Specimen Collecting Organisation and/or HCP may differ from the Requesting Organisation / HCP. For example, in the scenario where a patient is referred by their GP to attend a haematology clinic at a hospital.
-	The method used to transport the specimen(s) to the laboratory.
-	The processes that are used to handle missing or damaged specimens.
-	Whether the laboratory sends the test request and specimen(s) to another laboratory for analysis. These are known as send-away or referred tests. 
-	Whether the laboratory initiates further tests (using the supplied specimens) based on the results of the requested tests. For example, to provide a clearer interpretation of a result or to confirm a diagnosis. These are known as reflex tests.
-	Whether the test is performed at the point of care i.e. at or near the site of patient care rather than in a laboratory. 
-	Whether the test report is sent electronically or on paper.
-	Whether one or more interim reports are issued before a final report is sent to the Requesting Organisation.

Several key clinical scenarios are documented elsewhere in this guidance. These illustrate some of the variations in process outlined above, together with example test reports.

## Test Report Structure – Logical Data Model ##

The following entity diagram describes the logical data model that the National Pathology FHIR specification is based on:

{{render:pathologylogicaldatamodel}}

This model was developed jointly by the National Pathology, GP Connect and GP2GP teams within NHS Digital. The Test Report Filing entity relates to the process undertaken by the receiving health care professional when they review the test results and is not directly part of the scope of the National Pathology FHIR Messaging Specification. Please refer to the GP Connect pathology messaging guidance for further details.

The Test Report Document entity represents the test report in the format that it was received by the Requesting Organisation. The Test Result Document entity represents documents that form part of the test results, for example, images and charts. Both entities are out of scope for the current release but for completeness are included in the diagram.

The core pathology related entities are highlighted in dark blue. The remaining entities, outlined in light grey, represent the patient, and the organisations and practitioners associated with the pathology reporting process.

The following table summarises each of the core pathology entities:

| Entity Name | Description |
|--
|Test Report	|The summary data from the test report including the clinical interpretation|
|Test Group	|Output from a group of tests including the clinical interpretation|
|Test Result|	Output from a single test including the clinical interpretation|
|Specimen	|Information on the specimen tested.|
|Test Request Summary	|A summary of the original test request that is returned with the test report|

The Messaging Architecture section of this guidance describes how these business entities are represented in FHIR.


The Pathology information is exchanged using FHIR Bundles. This section shows the Bundle structure and the relationship between the resources which make up the Bundle. 

The Bundle uses the following resource to carry the related business entity information:
- **Test Request Summary** - This business entity is used to capture details from the requestor and uses the {{pagelink:ServiceRequest}} FHIR resource.
- **Test Report** - This business entity is used to capture details regarding all the tests performed by the performing organisation and uses the {{pagelink:DiagnosticReport}} FHIR resource.
- **Specimen** - This business entity is used to capture specimen (sample) details and uses the {{pagelink:Specimen}} FHIR resource.
- **Test Group** - This business entity is used to capture groups of test results. These can be a battery of tests or a single test, or a combination of all of these entities. It uses the {{pagelink:Observation}} FHIR resource.
- **Test Result** - This business entity is used to capture details for a single test result and uses the {{pagelink:Observation}}.

Each of these business entities is mapped to FHIR in the data mapping pages.
