## {{page-title}}

<div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b> Important:</b> The Acknowledgement Framework is currently a draft version. Please contact the <a href="mailto:interoperabilityteam@nhs.net?subject=Acknowledgement Framework">Interoperability Standards Team</a> if you are interested to discuss this solution for your use case.</div>

### Background

These are a collection of use case examples covering the transfer of patient medical records between two seperate GP systems as part of the GP2GP programme. This includes positive and negative acknowledgement responses. 

This use case uses the Messaging paradigm within FHIR.

## Use Case

| Use Case 1||
|--
| Name | GP2GP Record Transfer Acknowledgements |
| Description | This use case describes the process of acknowledging the outcome of a GP2GP patient record transfer between two New Market Entrant (NME) GP practices. The receiving practice (GP Practice B) must send an electronic notification to the sending practice (GP Practice A) to confirm whether the record transfer was successful, partially failed, or completely failed. Supporting documents referenced in the structured record must be retrieved separately via GP Connect 'Get Document' calls, and any failed document retrievals must also be acknowledged. |
| Actors (Role) | Receiving GP Practice (B), Sending GP Practice (A), MESH, Primary Care Support England (PCSE), GP Connect |
| Frequency of Use | Whenever a patient is transferred between NME GP practices |
| Triggers | GP Practice B **requests** a patient’s GP2GP record from GP Practice A via GP Connect. |
| Pre Conditions | - The patient is registered at GP Practice A <br />- GP Practice B has initiated a GP2GP transfer request for the patient’s record <br /> - GP Practice A has sent the requested GP2GP record to GP Practice B <br /> - GP Practice B is responsible for retrieving referenced documents separately using GP Connect Get Document |
| Post Conditions | - The GP2GP record transfer has been acknowledged by the receiving system as either successful, partially failed, or totally failed. <br /> - The sending practice (GP Practice A) has received a notification via MESH and may take further action if necessary <br /> - Any failed document retrievals have been acknowledged, and manual transfer via PCSE has been triggered if required. |
| Main Course | 1. GP Practice B requests the patient’s GP record from GP Practice A. <br /> 2. GP Practice A successfully sends the electronic GP record via GP Connect. <br /> 3. GP Practice B receives and integrates the record into its clinical system. <br /> 4. GP Practice B generates a success acknowledgement message. <br /> 5. GP Practice B sends the success acknowledgement via MESH to GP Practice A. <br /> 6. GP Practice A marks the transfer as complete in its system. <br /> 7. GP Practice B retrieves referenced documents separately via GP Connect Get Document. <br /> 8. Each document request succeeds or fails. |
| Alternate Course | 1. Steps 1–5 from the main flow occur. <br /> 2. GP Practice B retrieves referenced documents separately via GP Connect Get Document. <br /> 3. GP Practice B fails to retrieve some documents from GP Practice A. <br /> 4. GP Practice B generates a failure notification for each document that does not transfer successfully and a success acknowledgement for each that does. <br /> 5. GP Practice B sends the notifications via MESH to GP Practice A, listing the missing documents. <br /> 6. GP Practice A arranges for manual transfer of the missing documents via PCSE. |
| Exception | 1. GP Practice B requests the patient’s GP record from GP Practice A. <br /> 2. GP Practice A sends the record, but GP Practice B fails to integrate it due to validation errors or system failure. <br /> 3. GP Practice B generates a failure acknowledgement message. <br /> 4. GP Practice B sends the failure notification via MESH to GP Practice A. <br /> 5. GP Practice A marks the transfer as failed and may need to take corrective action. <br /> 6. If the structured record transfer fails, GP Practice A creates a task to print and send the full record via PCSE. |



## User Stories

### Successful GP2GP Record Transfer

**As an** NME GP Practice user at the provider site (losing practice) sending a patient record to another NME GP practice via GP Connect,<br />
**I want** to know if the GP2GP transfer has been successful,<br />
**So that** I am aware it is complete, and no further action is necessary.

**Acceptable Criteria:**

**Given** a patient is transferring from GP Practice A to GP Practice B,<br />
**And** GP Practice B requests the patient’s electronic GP record from GP Practice A,<br />
**When** GP Practice B receives and successfully files the GP record in their clinical system,<br />
**Then** GP Practice B shall send an electronic notification/acknowledgement to GP Practice A confirming that the record has been successfully received and filed,<br />
**And** GP Practice B shall acknowledge the success or failure of each referenced document retrieval via GP Connect Get Document.


### Notification for Missing Documents in Transfer

**As an** NME GP Practice user at the provider site (losing practice) sending a patient record to another NME GP practice via GP Connect,<br />
**I want** to know if the transfer has been successful, but some documents have not transferred, and which specific documents,<br />
So that I can print and ensure they are sent via Primary Care Support England (PCSE).


