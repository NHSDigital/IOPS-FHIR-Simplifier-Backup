### TES Alert to AuditEvent mapping

This table shows mappings from the TMS Event Serrvice (TES) Alert HL7v3 message to an SCR-Alert-AuditEvent profiled resource.


| data item             | card | data type  | target                                    | note                              |
|-----------------------|------|------------|-------------------------------------------|-----------------------------------|
| AlertEvent identifier | 1..1 | id II      | AuditEvent.entity.what                    | AlertEvent.id as AuditEvent.entity.what.identifier.value |
| ReasonType           | 1..1 | code cv    | AuditEvent.type                        | |
| ReasonCoded           | 1..1 | code cv    | AuditEvent.subtype                        | |
| ReasonText            | 0..1 | text st    | AuditEvent.outcomeDesc                    | |
| notificationMessage   | 0..1 | text st    | uses Extension-SCR-NotificationMessage    | |
| Patient               | 1..1 | id II      | AuditEvent.agent:Patient.who              | |
| OrganizationSDS       | 1..1 | id II      | AuditEvent.agent:Organization.who         | |
| Person                | 1..1 | id II      | AuditEvent.agent:Person.who               | User Id as AuditEvent.agent:Person.who.identifier.value |
| PersonRole            | 1..1 | desc ST    | AuditEvent.agent:Person.role              | Role Name as AuditEvent.agent:Person.role.codeableConcept.text |
| DeviceSDS             | 1..1 | name TN    | AuditEvent.source.observer.value          | ASID as AuditEvent.source.observer.value, ASID naming system as AuditEvent.source.observer.system |