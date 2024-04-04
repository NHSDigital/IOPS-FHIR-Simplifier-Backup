## {{page-title}}

This page details the interactions between systems, senders, receivers etc.  

## FHIR Workflow

The following pattern has been taken from the workflow management page on FHIR R4, linked above. The workflow broker is assumed to be the general architecture for the Genomic Medicine Service.

{{render:national-diagnostics-genetic-tests/restful-workflow}}

The Steps from the generalised pattern can be applied to a Genomic Medicine Service in the following way:

1. A Placer system (e.g. EHR), POSTs a UKCore-ServiceRequest to a broker (e.g. central GMS orders repository)
    a. The ServiceRequest needs to link to a UKCore-Patient, UKCore-PractitionerRole etc. 
    b. An associated Specimen will also need to be sent to the broker, linked to the ServiceRequest
    c. For WGS a UKCore-Consent should also be linked to the ServiceRequest for recording whether results can be used in research (defined as in scope for the programme).
2. The Broker notified of new request (without associated Task resources) via a subscription/internal logic
3. The Broker POSTs/creates Tasks on its own system, referencing the request resource, and seeking fulfilment from fillers (UKCore-Organisations, in the case of the GMS, the Home GLH)
4. The GLH system polls or is notified of an unassigned Task (according to routing rules)
5. The Filler PUTs an update to the Task to indicate it has been claimed/accepted
6. The Filler performs the requested tests/analyses, internal to LIMS (outside the scope of the central GMS), and updates (PUTs) Tasks as progress is made
7. As the final Tasks are fulfilled, the Filler POSTs a DiagnosticReport back to broker to record results (this implements the Event resource) once the analysis and interpretation has been performed
8. The Filler finally PUTs an update to its Task, changing the status to completed and pointing to UKCore-DiagnosticReport, which contains or points to the PDF
9. The workflow broker, either through subscriptions or via internal logic, retrieves details of placers to be notified of completed Tasks
10. A Placer polls for completed Tasks (or is notified of completed Tasks)
11. The Placer inspects results and updates ServiceRequest via PUT to indicate completion.

## Application to Genomics

The following sequence diagram represents the ideal workflow from submission of a test request to receipt of the fulfilling report:
{{render:nhs-digital-fhir-genomics-implementation-guide/diagams-gms-sequence-diagram}}

The numbered prefixes in the sequence diagram above translate to the following examples:

1. {{pagelink:Home/Examples/Subscription/Subscription-MinimalTaskNotification-Example.page.md}}
2. {{pagelink:Home/Examples/Bundle/Bundle-NonWGSTestOrderForm-Example.page.md}}
3. {{pagelink:Home/Examples/Subscription/Subscription-DiagnosticReportNotification-Example.page.md}}
4. {{pagelink:Home/Examples/Specimen/Specimen-BloodEDTA-Example.page.md}}
5. {{pagelink:Home/Examples/Task/Task-NonWGSRareDiseaseTestOrder-Example.page.md}} 
6. Same resource as in 5, posted to Home GLH, {{pagelink:Home/Examples/Task/Task-NonWGSRareDiseaseTestOrder-Example.page.md}} 
7. {{pagelink:Home/Examples/Task/Task-NonWGSRareDiseaseTestOrderAccepted-Example.page.md}}
8. Same resource as in 4, with additional accession ID and processing information, {{pagelink:Home/Examples/Specimen/Specimen-BloodEDTA-Example.page.md}}
9. Same resource as in 7, with updated businessStatus, {{pagelink:Home/Examples/Task/Task-NonWGSRareDiseaseTestOrderHold-Example.page.md}}
10. Get request for tasks with focus ServiceRequest (elaborated in API CapabilityStatement)
11. Same resource as in 9, posted to requester, {{pagelink:Home/Examples/Task/Task-NonWGSRareDiseaseTestOrderHold-Example.page.md}}
12. {{pagelink:Home/Examples/DiagnosticReport/DiagnosticReport-MichaelJonesReport-Minimal.page.md}}
13. Same resource as in 9, with updated status and businessStatus, {{pagelink:Home/Examples/Task/Task-NonWGSRareDiseaseTestOrderAccepted-Example.page.md}}
14. Same resource as in 12, posted to requester, {{pagelink:Home/Examples/DiagnosticReport/DiagnosticReport-MichaelJonesReport-Minimal.page.md}}
15. Same resource as in 2, with updated status to mark the ServiceRequest as filled, {{pagelink:Home/Examples/ServiceRequest/ServiceRequest-SavedTestOrderUpdated-Example.page.md}}

## Point-to-point messages

In the absence of a central broker, it is expected that requesting systems send the test order message directly to the Home GLH, which acts as the orchestrator for test requests within its region.

The Home GLH then has the responsibility to notify the requestor on status updates and assign subtasks to send-away labs where appropriate. In this case, as the original ServiceRequest bundle will not necessarily be retrievable from a central location, it is expected the Home GLH will forward the full test order alongside the Task for the send-away/downstream labs. 

DiagnosticReport bundles will then need to be sent back directly to the test requestor, via the GLH, rather than stored in a central repository.

It is expected that the structure of the messages will remain the same across both architectures.

In the overall architecture this approach is least favoured due to complexity of implementation across participating organisations and GLH's , even though it may offer local "quick wins" for early adoption of the FHIR messages with FOT (First of Type) implementations.

## Task Updates

One of the main challenges faced by a requester is the lack of visibility as regards test status once the test has been requested. Labs are also unable to track the status of the test once it leaves its organisational boundary and the interpretation and analysis may be completed at a different lab (send-away). 

The diagram below is a demonstration of how test and sample status will interact with end-to-end tasks, in the future-state. 

{{render:diagrams-test-status-updates}}

**Note:** The status examples given in the figure above, are unvalidated representations of what might typically be expected of the solution.

Examples shown include statuses such as:
- Test Order Sent
- Test Order Received
- Test and Sample Aligned
- Preparing Sample 
- Order Forward Message Received
- Genomic Analysis Completed
- Requires MDT
- MDT Concluded
- Report sent (Home GLH)
- Report sent (Requester)
- Report Received (Requester)

**Note:** The Interoperability project will be validating these test statuses through the alpha (development) phase. Further input is required from the GMS to clarify if the statuses are appropriate and defining of the business rules will be included in the Alpha phase.

The requirement for interoperability is to provide test status updates at the point when the activity leaves and is received at the next organisational boundary. This will require LIMS systems to be able to tie in with the central broker and provide updates on the status of the test request. 

In the solution proposed all updates to tasks in terms of their statuses are expected to be manually driven by organisation controls. The central service will have limited capability to automatically update organisation tasks on their behalf. This is to avoid IG issues and ensure
provenance is managed accurately.

### Automated updates

The test order system will automatically update some resources when certain actions or conditions are met. The current list (not final) of actions are as follows:

|Resource Change|Test Order Service triggered changes|
|--|--|
|ServiceRequest created|Creation of Task resource assigned to the target GLH.|
|ServiceRequest updated with a status set to “completed”|This will indicate the test request has been completed and therefore all tasks and sub-tasks linked to the ServiceRequest will be updated with a status of “completed”.|
|Specimen Task updated with link to Specimen|Update to ServiceRequest to also reference the Specimen details added.|
|DiagnosticReport Created with a status of “final”|This will indicate the final report is complete and therefore all tasks linked to the ServiceRequest have been completed, therefore the all tasks and sub-tasks linked to the ServiceRequest will be updated with a status of “completed”.|
|ServiceRequest updated with a status set to “Entered in Error”|All tasks and sub-tasks of that ServiceRequest will be update with a status of “entered-in-error”|
|ServiceRequest updated with a status set to “revoked”|All tasks and sub-tasks of that ServiceRequest will be update with a status of “cancelled”|

## Sample Tracking

Test requests may have none, single or multiple associated samples. Alternatively, multiple tests may be requested and may use a single sample. An additional challenge exists on the management and tracking of samples within the regional boundaries or when samples are sent away. There is a lack of visibility to the requester if the sample has been received by the lab or when it is forwarded to another lab. The central infrastructure will enable the tracking of samples once dispatched or received by an organisation. 

From a sample status standpoint, the update provided at each organisational boundary will be:
- Sample Sent
- Sample Received 

Or

- Sample Not Required (in the instance such as re-analysis)

The test and sample statuses required will be further refined based on confirmation from the business and will be reflected in this business rules document. 
From a functional requirement standpoint for both test status and sample tracking, the requirement is to provide the capability to review all tests and associated samples at a GLH level and provide the ability to run queries at a patient level and run any queries on the test request as well as associated samples. 