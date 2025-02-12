## {{page-title}}

## Current State

In terms of messages sent between organizational boundaries, this can be represented using the figure below:

{{render:diagrams-current-state}}

- A requester will create and submit a test request on paper (Org Boundary 1)
- A sample is also then requested to be collected at a different location (Org Boundary 2). A variety on non-standardised communication means are employed.
- Once collected, the sample will be sent across to the GLH (Org Boundary 3) along with a sample linkage form (paper). 
- The test request and sample may arrive at different times at the GLH. If the test is a specialist request, the test along with the sample will be forwarded to another lab (Org Boundary 4, in this example, the remote region GLH) for processing.
- In this example the remote GLH, also forwards on the test request and sample to another lab in the region (Org Boundary 5).

As data collection is predominantly paper based, there is a lack of overall visibility for the requester as to when the test has been received by the lab along with the sample and the overall process. From a GLH perspective, when the test is sent away, the GLH no longer has any visibility on the status of the test request as all communication is currently analogue. 

## Intended Future State

### Order Messaging

{{render:diagrams-future-state}}

Interoperability addresses the challenge faced in the communication of data across organisational boundaries through the set-up of a central service for the management of messages across organisational boundaries. Furthermore, by enabling electronic test requesting (either via integration of existing systems to the central service, or a national portal), the GLH has visibility of any test requested in near real-time, including situations where the sample has not been received. 

The figure above takes the current state example and applies the future, interoperable state, as proposed by the target architecture. The transmission flows depicted are described below:
- A requester places a test request electronically (Org Boundary 1).
  - A sample is also then requested to be collected at a different location (Org Boundary 2)
  - A variety on non-standardised communication means are employed.  i.e., Current state remains applicable.
- The GLH (Org Boundary 3) is immediately notified of the test request via the central service.
- The sample collecting organisation (Org Boundary 2) is able to update the order, using a test request identifier, adding the sample information.
  - Once collected, the sample will be sent across to the GLH (Org Boundary 3). Despite sample details being updated electronically (3), standard procedure is followed and a sample linkage form (paper), is still sent with the sample. 
- Once the sample has been collected (Org Boundary 2), the central service enables and updates a message to the GLH, indicating that the sample has been sent. 
- When the sample arrives at the GLH (Org Boundary 3), the example assumes the GLH now has both test data and sample data. I.e., the minimum data required to process an order. This complete dataset is forwarded to the remote GLH (Org Boundary 4) via the central service.  
  - The sample is forwarded to the remote GLH also. The physical sample is sent via existing, current-state logistical means.
- The Remote GLH receive the test request and sample data via the central service.  
- In this example the remote GLH, also forwards on the test request and sample to another lab in the region (Org Boundary 5). In the future state it does so via central service messaging.
  - The sample is forwarded to the remote GLH also. The physical sample is sent via existing, current-state logistical means.
- The remote lab processing the sample and fulfilling the order(Org Boundary 5) in this example, receives the forwarded electronic order data.

Once a sample has been analysed and interpreted, a final report once generated, can provide an update via the central service to the requester (Org Boundary 1) and the GLH (Org Boundary 3) via the central service. 

### Test Status Messaging 

{{render:diagrams-test-status-messaging}}

The figure above takes the current state example and applies the future, interoperable state for test status update messaging, as proposed by the target architecture. The transmission flows depicted are described below:
- When the electronic order is submitted from (Org Boundary 1), an ‘Order Sent’ status update is provided in parallel.
- Once received at the GLH (Org Boundary 3), the GLH lab issues a test status update of ‘Order Received’.  
- By way of example, the GLH is also shown to issue an update of ‘Awaiting Sample’ whilst the physical sample is not yet received from (Org Boundary 2).
- Upon forwarding the order (sending away) to the remote GLH, the Home GLH updates the status of the test to ‘Order Forwarded’.
- The order receipt is reflected in the first status update of the remote GLH (Org Boundary 4).
- By way of example, the Remote GLH is also shown to issue an update of ‘Awaiting Sample’ whilst the physical sample is not yet received from the Home GLH (Org Boundary 3).
- The Remote GLH forwards the order to another lab (Org Boundary 5), local to its own region.
- The Lab (Org Boundary 5) updates as ‘Order Received’.
- By way of example, one of the tasks the Lab may be responsible for is Sequencing.  Updates are made accordingly. E.g.  ‘Sequencing’.
- As a final example of order fulfilment tasks being completed, the Lab authorises a results report and issues an update to this effect.

### Sample Status Messaging

{{render:diagrams-sample-status-messaging}}

The figure above takes the current state example and applies the future, interoperable state for sample status update messaging, as proposed by the target architecture. The transmission flows depicted are described below:

- When the electronic order is submitted from (Org Boundary 1), a ‘Sample Sent’ status update is provided in parallel.
- Once received at the GLH (Org Boundary 3), the GLH lab issues a sample status update of ‘Sample Received’.  
- As the order/sample is being sent away to a Remote GLH (Org Boundary 4), the sample status is updated to ‘Sample Sent’ at this time. Note, corresponding organisational identifiers will feature in update messages as well as timestamps.
- Once the Remote GLH (Org Boundary 4) receives the physical sample, a status update of ‘Sample Received’ is given.
- Upon sending the order and sample on to another lab (Org Boundary 5) to fulfil the processing, a ‘Sample Sent’ message is issued/updated.
- The Lab (Org Boundary 5) updates as ‘Sample Received’, upon receipt of the physical sample.

### Note on Routing of Samples and Data

Messages sent to the core broker constitute data only, including data on where physical samples are or have been sent to (see {{pagelink:Profile-UKCore-Specimen}} and {{pagelink:Profile-Genomics-Task}} for more details on how location/tracking data is represented).

Test Requests and Samples can be sent to separate organizations based upon local/regional processes. Linkage between samples and test requests allow the organizations responsible for fulfillment of a test request to gain visibility on where physical specimens are. e.g. Sample Processing Task assigned to Org 5, `Task.input` will then contain a reference to the Specimen resource and hold tracking information, while management of the test order remains with Org 3 (which is marked as the `owner` of the Process Test Request Task). The full Test Request will be linked from all Tasks through the `Task.focus` field.

The current iteration of the NGTP assumes routing of a report back to the requesting clinician via the Home GLH. While this has been represented within the design, the FHIR architecture supports any organization attaching DiagnosticReports and completing the Report Distribution Task, which may be needed to support other use cases, such as rapid testing etc.

Cellular Pathology Genomic Centres will be considered owners of initial Sample Preparation Tasks where samples are routed through CPGCs. In this case Cellular Pathology will be considered the Test Requester. Requesters will be referenced from the Test Request through SDS User ID (CIS2 Identity), thereby removing the need to register requesters on lab systems. Additional reporting addresses can be added through both the `ServiceRequest.extention:additionalContact` as well as `PractitionerRole.telecom`. Additionally, any organization can poll for updates (or in future subscribe to events) related to Test Requests they are interested in, subject to Information Governance controls, which would allow distribution to organizations outside th original requester.
