## {{page-title}}

<div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b> Important:</b> The Acknowledgement Framework is currently a draft version. Please contact the <a href="mailto:interoperabilityteam@nhs.net?subject=Acknowledgement Framework">Interoperability Standards Team</a> if you are interested to discuss this solution for your use case.</div>

Currently, the Acknowledgement Framework only provides guidance for the Messaging paradigm. However, the plan is to provide guidance and support for the Documents and RESTful paradigms in a future version.

Profiles and extension resources used within the Acknowledgement Framework are, by default, derived from UK Core. Where a FHIR asset does not exist in UK Core, then the Acknowledgement Framework will derive from the base International standard.

## Response patterns (pre-agreed between two systems)

There is an expectation most use-cases will involve both the sending and receiving systems to be aware of the rules and circumstances that govern when, and how, acknowlegdements are sent and received. For example, System A and System B have been designed and built according to the agreed system rules that for any time a Message is received, then a positive or negative acknowlegdment is sent.

<br />
<plantuml>
title "Request and receive all positive and negative acknowledgements"
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
...
end note
receiver --> sender: Message acknowledgement(s)
note right
MessageHeader.id: **0002**
MessageHeader.response.identifier: **0001**
MessageHeader.response.code: **ok**
...
end note
</plantuml>
<br />

| Sender | Message Flow Action | Receiver |
| - | ------------------- | -------- |
| 1..1 &rarr; | Send message payload | Payload received |
| Acknowledgement(s) received | Send acknowledgement(s)        | &larr; 1..*   |

<br /><br />

<plantuml>
title "Request and receive only negative acknowledgements"
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
...
end note
receiver --> sender: Message acknowledgement(s)
note right
MessageHeader.id: **0002**
MessageHeader.response.identifier: **0001**
MessageHeader.response.code: **error**
OperationOutcome.issue.severity: **error**
OperationOutcome.issue.code: **invalid**
...
end note
</plantuml>

<br />

| Sender | Message Flow Action | Receiver |
| ----------- | ------------------- | -------- |
| 1..1 &rarr;       | Send message payload | Payload received |
| Acknowledgement(s) received   | Send negative acknowledgement(s)        | &larr; 0..*   |

<br /><br />

<plantuml>
title "Request and receive only positive acknowledgements"
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
...
end note
receiver --> sender: Message acknowledgement(s)
note right
MessageHeader.id: **0002**
MessageHeader.response.identifier: **0001**
MessageHeader.response.code: **ok**
OperationOutcome.issue.severity: **information**
OperationOutcome.issue.code: **informational**
...
end note
</plantuml>

<br />

| Sender | Message Flow Action | Receiver |
| ----------- | ------------------- | -------- |
| 1..1 &rarr;       | Send message payload | Payload received |
| Acknowledgement(s) received   | Send positive acknowledgement(s)        | &larr; 0..*   |

<br /><br />

<plantuml>
title "Request and receive no positive or negative acknowledgements (fire and forget)"
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
...
end note
</plantuml>

<br /><br />
## Response patterns (NOT pre-agreed between two systems)

Although there would likely be very few use cases where both sending and receiving systems cannot agree beforehand their acknowledgement response patterns, the Acknowledgement Framework provides additional functionality to include an extension that states what type of acknowledgement a system expects to receive.

<br />
<plantuml>
title "Request and receive all positive and negative acknowledgements"
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **always** 
...
end note
receiver --> sender: Message acknowledgement(s)
note right
MessageHeader.id: **0002**
MessageHeader.extension.
messageheader-response-request.
valueCode: **never**
MessageHeader.response.identifier: **0001**
MessageHeader.response.code: **ok**
...
end note
</plantuml>
<br />

| Sender | Message Flow Action | Receiver |
| - | ------------------- | -------- |
| 1..1 &rarr; | Send message payload | Payload received |
| Acknowledgement(s) received | Send acknowledgement(s)        | &larr; 1..*   |

<br /><br />

<plantuml>
title "Request and receive only negative acknowledgements"
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **on-error** 
...
end note
receiver --> sender: Message acknowledgement(s)
note right
MessageHeader.id: **0002**
MessageHeader.extension.
messageheader-response-request.
valueCode: **never**
MessageHeader.response.identifier: **0001**
MessageHeader.response.code: **error**
OperationOutcome.issue.severity: **error**
OperationOutcome.issue.code: **invalid**
...
end note
</plantuml>

<br />

| Sender | Message Flow Action | Receiver |
| ----------- | ------------------- | -------- |
| 1..1 &rarr;       | Send message payload | Payload received |
| Acknowledgement(s) received   | Send negative acknowledgement(s)        | &larr; 0..*   |

<br /><br />

<plantuml>
title "Request and receive only positive acknowledgements"
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **on-success** 
...
end note
receiver --> sender: Message acknowledgement(s)
note right
MessageHeader.id: **0002**
MessageHeader.extension.
messageheader-response-request.
valueCode: **never**
MessageHeader.response.identifier: **0001**
MessageHeader.response.code: **ok**
OperationOutcome.issue.severity: **information**
OperationOutcome.issue.code: **informational**
...
end note
</plantuml>

<br />

| Sender | Message Flow Action | Receiver |
| ----------- | ------------------- | -------- |
| 1..1 &rarr;       | Send message payload | Payload received |
| Acknowledgement(s) received   | Send positive acknowledgement(s)        | &larr; 0..*   |

<br /><br />

<plantuml>
title "Request and receive no positive or negative acknowledgements (fire and forget)"
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **never** 
...
end note
</plantuml>

<br />

| Sender | Message Flow Action | Receiver |
| ----------- | ------------------- | -------- |
| 1..1 &rarr; | Send message payload | Payload received |
| No acknowledgement(s) received | No acknowledgement(s) sent   | &larr; 0..0   |

<br />

## Multiple acknowledgements

As illustrated in the response patterns diagrams, the Acknowledgement Framework facilitates the abilitity to send multiple acknowledgements.

Further guidance and diagrams will be added specifically for this in the future.

<br />

## Technical and business acknowledgements

The Acknowledgement Framework provides the ability to return 'technical' and 'business' acknowledgements.

For a 'positive' business acknowledgement, code **ok** from CodeSystem **ResponseType**; code **information** from CodeSystem **IssueSeverity**; **informational** from CodeSystem **IssueType**; and (currently proposed) code **BUSINESS_SUCCESS** from CodeSystem **operation-outcome** can be used to specifically imply that the positive acknowledgement is a 'business' acknowledgement.

For a 'negative' business acknowledgement, code 'fatal-error' from CodeSystem **ResponseType**, code **fatal-error** from CodeSystem **IssueSeverity**; **business-rule** from CodeSystem **IssueType**; and (currently proposed) code **BUSINESS_FAIL**  (or a more detailed business failure code) from CodeSystem **operation-outcome** can be used to specifically imply that the negative acknowledgement is a 'business' acknowledgement. 

<plantuml>
title "Positive business acknowledgement"
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **always**
...
end note
receiver --> sender: Message acknowledgement(s)
note right
MessageHeader.id: **0002**
MessageHeader.extension.
messageheader-response-request.
valueCode: **never**
MessageHeader.response.identifier: **0001**
MessageHeader.response.code: **ok**
OperationOutcome.issue.severity: **information**
OperationOutcome.issue.code: **informational**
OperationOutcome.issue.details.coding: **BUSINESS_SUCCESS**
...
end note
</plantuml>

<br /><br />

<plantuml>
title "Negative business acknowledgement"
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **always**
...
end note
receiver --> sender: Message acknowledgement(s)
note right
MessageHeader.id: **0002**
MessageHeader.extension.
messageheader-response-request.
valueCode: **never**
MessageHeader.response.identifier: **0001**
MessageHeader.response.code: **fatal-error**
OperationOutcome.issue.severity: **fatal OR error**
OperationOutcome.issue.code: **business-rule**
OperationOutcome.issue.details.coding: **BUSINESS_FAIL**
...
end note
</plantuml>

<br /><br />
## Describing errors

Where possible, additional information SHALL be included to describe errors. This will help receiving systems understanding the errors in more detail. Errors can be described by using OperationOutcome.issue.diagnostics and OperationOutcome.issue.expression.

An example below shows how this can be used. 

<plantuml>
title "Mandatory element is missing" 
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **always**
...
end note
receiver --> sender: Message acknowledgement(s)
note right
MessageHeader.id: **0002**
MessageHeader.extension.
messageheader-response-request.
valueCode: **never**
MessageHeader.response.identifier: **0001**
MessageHeader.response.code: **fatal-error**
OperationOutcome.issue.severity: **error**
OperationOutcome.issue.code: **required**
OperationOutcome.issue.diagnostics: **Line 2345. Mandatory element Observation.status is missing.**
OperationOutcome.issue.expression: **Observation.status**
OperationOutcome.issue.details.coding: **TECHNICAL_FAIL**
...
end note
</plantuml>

<br />

## Point-to-point and multi-hop

Further guidance and diagrams will be added specifically for this in the future.

<br />

## Response codes

This guidance should be followed to determine what issue codes are most appropriate to be used for each response code.

### ok

| Element | Code |
| ------- | ---- |
| MessageHeader.response.code | ok |
| OperationOutcome.issue.severity | information OR warning |
| OperationOutcome.issue.code | informational |

### transient-error

| Element | Code |
| ------- | ---- |
| MessageHeader.response.code | transient-error |
| OperationOutcome.issue.severity | fatal |
| OperationOutcome.issue.code | transient (and sub-errors) |

### fatal-error

| Element | Code |
| ------- | ---- |
| MessageHeader.response.code | fatal-error |
| OperationOutcome.issue.severity | fatal OR error |
| OperationOutcome.issue.code | invalid (and sub-errors) OR security (and sub-errors) OR processing (and sub-errors) |




