---
topic: Message Interaction
---
## Message Interaction

To claim self-conformance of implementation of the Acknowledgement Framework, there are a limited number interaction which shall be supported where appropriate. You may find the full list of these interaction [here](https://simplifier.net/guide/Acknowledgement-Framework/Home/Design/Interactions.page.md?version=current)



---
topic: Example Scenarios
---
## Example Scenarios
An example GP patient registration is provided [here](https://simplifier.net/guide/Acknowledgement-Framework/Home/Examples/GP-Patient-Registration?version=current)

**Scenario 1:** GP B sends a HbA1c (Haemoglobin A1c) request Message to LAB A where messageheader-response-request.value is 'always'. LAB A receives the Message and determines that the Message has no technical issues. LAB A responds with a Message where MessageHeader.response.code is 'ok'. | <plantuml>
participant "GP B" as sender
participant "LAB A" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **always** 
...
end note
receiver --> sender: Message acknowledgement
note right
MessageHeader.id: **0002**
MessageHeader.extension.
messageheader-response-request.
valueCode: **never**
MessageHeader.response.identifier: **0001**
MessageHeader.response.code: **ok**
OperationOutcome.issue.severity: **information**
OperationOutcome.issue.code: **Informational**
OperationOutcome.issue.details.coding.code: **TECHNICAL_SUCCESS**

...
end note
</plantuml> |

Example Request Message 

Example Response Message

**Scenario 1:** GP B sends a HbA1c (Haemoglobin A1c) request Message to LAB A where messageheader-response-request.value is 'always'. LAB A receives the Message and determines that the Message has no technical issues. LAB A responds with a Message where MessageHeader.response.code is 'ok'. | <plantuml>
participant "GP B" as sender
participant "LAB A" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **always** 
...
end note
receiver --> sender: Message acknowledgement
note right
MessageHeader.id: **0002**
MessageHeader.extension.
messageheader-response-request.
valueCode: **never**
MessageHeader.response.identifier: **0001**
MessageHeader.response.code: **transient-error**
OperationOutcome.issue.severity: **fatal**
OperationOutcome.issue.code: **transient**
OperationOutcome.issue.details.coding.code: **BUSINESS_FAIL**

...
end note
</plantuml> |

List of the potential other failures

**Propose the following to be added to CodeSystem operation-outcome:**

| Code | Display | Definition |
| ---- | ------- | ---------- |
| **UNRECOGNISED_RECIPIENT** | Recipient is not recognised | Recipient is not recognised |
| **UNRECOGNISED_SENDER** | Sender is not recognised | Sender is not recognised |
| **NOT_APPROVED_ATTACHMENT_FILE_TYPE** | Attachment file type is not approved | Attachment file type is not approved |
| **UNSUPPORTED_ATTACHMENT_FILE_TYPE** | Attachment file type is not supported | Attachment file type is not supported |
| **DUPLICATE_BUNDLE_ID** | Bundle id is a duplicate | Bundle id is a duplicate |
| **EXCESSIVE_SIZE** | Payload size is too large | Payload size is too large |
| **TECHNICAL_SUCCESS** | Request successfully received | Request successfully received and no technical issues were identified |
| **BUSINESS_SUCCESS** | Business request successfully actioned | A person has successfully actioned the request. |
| **BUSINESS_FAIL** | Busines request not actioned | A person has declined to action the request. |
| **BUSINESS_FAIL_DATA_INAPPROPRIATE** | Data is inappropriate | The data makes no sense, dubious, contradictory, using foreign language, or other similar issues. |
| **BUSINESS_FAIL_RECIPIENT_INAPPROPRIATE** | Recipient is inappropriate | The recipient of the request cannot, or should not, action the request. |
| **BUSINESS_FAIL_SENDER_INAPPROPRIATE** | Sender is inappropriate | The sender of the request should not have sent the request (e.g. missing relevant qualifications). |
| **BUSINESS_FAIL_ALREADY_EXISTS** | Not added or registered because already exists | The specified person, entity, process, or other similar concept, cannot be added or registered because they/it already exists on the system. |
| **BUSINESS_FAIL_MAX_CAPACITY** | System has reached maximum capacity | The specified person, entity, process, or other similar concept, cannot be added or registered because the system has reached its maximum capacity. |
| **BUSINESS_FAIL_NOT_ALLOWED** | Not added or registered because is not allowed | The specified person, entity, process, or other similar concept, is not allowed to be added or registered (e.g. a patient is banned). |
| **PATIENT_KNOWN** | Patient is known and registered at this clinical setting | Patient is known and registered at this clinical setting |
| **PATIENT_NOT_KNOWN** | Patient is not known or registered at this clinical setting | Patient is not known or registered at this clinical setting |
| **PATIENT_PREVIOUSLY_KNOWN** | Patient is no longer at this clinical setting | Patient is no longer at this clinical setting |
| **PATIENT_KNOWN_AND_DECEASED** | Patient is known at this clinical setting but has recently deceased | Patient is known at this clinical setting but has recently deceased |
