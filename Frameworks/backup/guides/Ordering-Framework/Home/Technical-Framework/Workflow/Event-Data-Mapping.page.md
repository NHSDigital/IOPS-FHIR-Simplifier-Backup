## {{page-title}}

For backwards compatibility it is recommended that the HL7 v2 Event Trigger types {{link:http://terminology.hl7.org/CodeSystem/v2-0003}} is supported for **type**.

| Method | type | Subject | source | time | data |
|--
| Multicast Notification Service | type | subject | source | time | data |
| FHIR Cast | event.hub.event |  |  | timestamp | event.context |
| Subscription Message | MessageHeader.event | | MessageHeader.source | Bundle.timestamp | Bundle.entry[] depends on MessageHeader.event |
| FHIR Workflow Task | Task.code | Task.for.identifier | Http Header | Task.meta.lastUpdated | Task.focus |
| HL7 v2 ADT | MSH.9 - Message Type | PID - Patient identification | MSH.3 - Sending Application </br> MSH.4 - Sending Facility | EVN.2 - Recorded Date/Time | Depends on Message.type |