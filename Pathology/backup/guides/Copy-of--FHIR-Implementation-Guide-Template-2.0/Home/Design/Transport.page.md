---
topic: Transport
---
## Transport
### Transactions sent to primary Care (GP)
The Message Exchange for Social Care and Health (MESH) is the primary communication tool utilized in the health and social care sector. It operates on the Spine infrastructure and is used for transferring electronic messages directly between applications, allowing for secure communication between different organizations. An example of its use is when pathology labs send test results to GP practices via MESH. It has replaced the Data Transfer Service (DTS).

Users access MESH either through the MESH client or through integrated systems that use the Application Programming Interface (API). Most of the time, the setup of MESH is managed by the system suppliers or IT administrators for each organization, so end-users should reach out to their organization's IT contacts for any questions about the service.

Currently the only method to send a message (document) to a GP is via MESH as the transport mechanism. Each MESH document is sent using a MESH workflow ID. Both sender and receiver (responder) MUST use the associated ID;

#### MESH WorkflowIDs
| **Use Case** | **Sender MESH WorkflowID** | **Receiver (Responder) MESH WorkflowID**|
|--
| Pathology Blood Science and Microbiology R4 | PATH_BS_R4 | PATH_BS_R4_ACK |
| Pathology Cellular R4| PATH_CELL_R4 | PATH_CELL_R4_ACK |
| Pathology Genetics R4 | PATH_GN_R4 | PATH_GN_R4_ACK |


Please refer to [MESH endpoint lookup service and WorkflowIDs]( https://digital.nhs.uk/services/message-exchange-for-social-care-and-health-mesh/mesh-guidance-hub/endpoint-lookup-service-and-workflowids). The endpoint lookup service allows Messaging Exchange for Social Care and Health (MESH) users to identify the name of a MESH mailbox to send a MESH message.

Also the complete [MESH guide and how to use it]( https://digital.nhs.uk/services/message-exchange-for-social-care-and-health-mesh/mesh-guidance-hub) can be found on MESH website. 