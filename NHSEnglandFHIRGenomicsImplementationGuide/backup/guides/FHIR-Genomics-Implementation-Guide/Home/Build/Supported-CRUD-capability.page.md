# {{page-title}}

Interactions supported by the API are defined within the {{pagelink:Home/FHIRAssets/CapabilityStatements/Instance.page.md}} CapabilityStatement. 

Expected patterns for responses based on Transaction vs. Individual Resource, HTTP Verbs used and Success vs. Failure are detailed in {{pagelink:acknowledgementsandresponses}}.

## Create
The main create operations will be creation of the initial test request and associated clinical information; creation of interim data (either binary files or structured FHIR resources attached to Task.output; and creation of the resulting DiagnosticReport resources. Creation of ServiceRequest and DiagnosticReport resources will trigger the associated processes to kick-off or close down a test order fulfilment workflow.

### Common Interaction Patterns

#### Creation of Test Order

<plantuml>
@startuml
Participant EPR as "Requester (EPR)"
Participant GOMS as "Genomic Order Management Service Broker"
Participant LIMS as "Fulfilling Organization (GLH/LIMS)"
EPR -> GOMS : POST Test Order Transaction Bundle
alt Success
GOMS -> GOMS : Create Tasks for Test Order
GOMS --> EPR : Transaction Response Bundle containing created resources
opt Event Notification
GOMS -> LIMS : POST event-notification Bundle (new tasks for org)
end
else Failure
GOMS --> EPR : Transaction Response Bundle containing OperationOutcomes with diagnostics
end
@enduml
</plantuml>

#### Creation of Genomic Report

<plantuml>
@startuml
Participant LIMS as "Fulfilling Organization (GLH/LIMS)" order 30
Participant GOMS as "Genomic Order Management Service Broker" order 20
Participant EPR as "Requester (EPR)" order 10
LIMS -> GOMS : POST Genomic Report Transaction Bundle
alt Success
GOMS --> LIMS : Transaction Response Bundle containing created resources
opt Event Notification
GOMS -> EPR : POST event-notification Bundle (report available)
end
else Failure
GOMS --> LIMS : Transaction Response Bundle containing OperationOutcomes with diagnostics
end
@enduml
</plantuml>

#### Addition of Consent/RoD

<plantuml>
@startuml
Participant EPR as "Requester (EPR)"
Participant GOMS as "Genomic Order Management Service Broker"
Participant LIMS as "Fulfilling Organization (GLH/LIMS)"
EPR -> GOMS : POST Consent/ROD Transaction Bundle \n(including update to ServiceRequest.supportingInfo to reference Consent\n and Provenance detailing change to ServiceRequest)
alt Success
GOMS --> EPR : Transaction Response Bundle containing created resources
opt Event Notification
GOMS -> LIMS : POST event-notification Bundle (Test Order updated)
end
else Failure
GOMS --> EPR : Transaction Response Bundle containing OperationOutcomes with diagnostics
end
@enduml
</plantuml>

#### Addition of Specimen

<plantuml>
@startuml
Participant EPR as "Requester (EPR)"
Participant GOMS as "Genomic Order Management Service Broker"
Participant LIMS as "Fulfilling Organization (GLH/LIMS)"
alt Transaction
EPR -> GOMS : POST Specimen Transaction Bundle \n(including update to ServiceRequest.supportingInfo to reference Specimen)
alt Success
GOMS -> GOMS : Addition of Specimen to relevant Tasks \n(could be performed manually)
GOMS --> EPR : Transaction Response Bundle containing created resources
opt Event Notification
GOMS -> LIMS : POST event-notification Bundle (Test Order updated)
end
else Failure
GOMS --> EPR : Transaction Response Bundle containing OperationOutcomes with diagnostics
end
else Single Resource
EPR -> GOMS : POST Specimen 
alt Success
GOMS --> EPR : Response with created resource
EPR -> GOMS : POST Transaction Bundle updating ServiceRequest.supportingInfo \nand adding Provenance
alt Success
GOMS -> GOMS : Addition of Specimen to relevant Tasks \n(could be performed manually)
GOMS --> EPR : Transaction Response Bundle containing created resources
opt Event Notification
GOMS -> LIMS : POST event-notification Bundle (Test Order updated)
end
else Failure
GOMS --> EPR : Transaction Response Bundle containing OperationOutcomes with diagnostics
end
else Failure
GOMS --> EPR : OperationOutcome response with diagnostics
end
end

@enduml
</plantuml>

#### Creation of new Task

<plantuml>
@startuml
Participant LIMS as "Fulfilling Organization (GLH/LIMS)" order 20
Participant GOMS as "Genomic Order Management Service Broker" order 10
LIMS -> GOMS : POST Task referencing ServiceRequest
alt Success
GOMS --> LIMS : Response with created resource
else Failure
GOMS --> LIMS : OperationOutcome response with diagnostics
end
@enduml
</plantuml>

## Read
From initial design work, it is expected the main use case will be labs and requestors polling the central service for test orders and reports, including associated clinical information, as well as polling the system for the current state of Tasks and Task update history, through associated AuditEvents and Provenance resources.

### Common Patterns

#### Searching for Tasks by Org (Polling for tasks)

<plantuml>
@startuml
Participant LIMS as "Fulfilling Organization (GLH/LIMS)" order 20
Participant GOMS as "Genomic Order Management Service Broker" order 10
alt Only matching resources
LIMS -> GOMS : GET Task with owner=<ods_code> 
GOMS --> LIMS : Searchset Bundle response with matching resources
else Additional includes
LIMS -> GOMS : GET Task with owner=<ods_code> and _include=Task:focus
GOMS --> LIMS : Searchset Bundle response with matching resources \nand included referenced ServiceRequests
end
@enduml
</plantuml>

#### Searching for ServiceRequest by Patient

<plantuml>
@startuml
Participant LIMS as "Fulfilling Organization (GLH/LIMS)" order 20
Participant GOMS as "Genomic Order Management Service Broker" order 10
LIMS -> GOMS : GET ServiceRequest with subject=<nhs_number> 
GOMS --> LIMS : Searchset Bundle response with matching resources
@enduml
</plantuml>

#### Retrieving Test Orders

<plantuml>
@startuml
Participant LIMS as "Fulfilling Organization (GLH/LIMS)" order 20
Participant GOMS as "Genomic Order Management Service Broker" order 10
opt
LIMS -> GOMS : Search for ServiceRequest to get ID 
end
LIMS -> GOMS : GET ServiceRequest/<id>/ with $graph?graph=genomics-test-order 
GOMS --> LIMS : Collection Bundle response with resources referenced in the graph
@enduml
</plantuml>

#### Retrieving DiagnosticReport by ID

## Update
A large part of the interactions with the central service, over the course of order fulfilment, will be updates to Task resources, which constitute status updates. These events will be captured by the central broker through AuditEvent resources. Additionally, ServiceRequest and DiagnosticReport resources may be updated if tests need to be changed or new data added. Reasons for changed SHOULD be captured through Provenance resources. The impact these updates have on work-in-progress will be defined within Business Rules on the central broker (including how cancellations are managed).

### Common Patterns

#### Update Task Status

<plantuml>
@startuml
Participant LIMS as "Fulfilling Organization (GLH/LIMS)" order 20
Participant GOMS as "Genomic Order Management Service Broker" order 10
opt
LIMS -> GOMS : Search for Task to get ID 
GOMS --> LIMS : Searchset Bundle response with matching resources
end
LIMS -> GOMS : PUT Task with new status/businessStatus/input/output
alt Success
GOMS -> GOMS : Create AuditEvent to track change \nand increment resource version
GOMS --> LIMS : Response with updated resource
else Failure
GOMS --> LIMS : OperationOutcome response with diagnostics \ne.g. unsupported state transition
end
@enduml
</plantuml>

#### Reassign Task

<plantuml>
@startuml
Participant LIMS as "Fulfilling Organization (GLH/LIMS)" order 20
Participant LIMS2 as "Sendaway Organization (remote GLH/LIMS)" order 30
Participant GOMS as "Genomic Order Management Service Broker" order 10
opt
LIMS -> GOMS : Search for Task to get ID 
GOMS --> LIMS : Searchset Bundle response with matching resources
end
LIMS -> GOMS : PUT Task with new owner
alt Success
GOMS -> GOMS : Create AuditEvent to track change \nand increment resource version
GOMS --> LIMS : Response with updated resource
alt Polling
LIMS2 -> GOMS : GET Task with owner=<ods_code>
GOMS --> LIMS2 : Searchset Bundle response with matching resources
else Event Notification
GOMS -> LIMS2 : POST event-notification Bundle (new tasks for org)
end
else Failure
GOMS --> LIMS : OperationOutcome response with diagnostics \ne.g. unsupported state transition
end
@enduml
</plantuml>

#### Completion of Task with Output Reference

<plantuml>
@startuml
Participant LIMS as "Fulfilling Organization (GLH/LIMS)" order 30
Participant GOMS as "Genomic Order Management Service Broker" order 20
Participant EPR as "Requester (EPR)" order 10
opt
LIMS -> GOMS : Search for Task to get ID 
GOMS --> LIMS : Searchset Bundle response with matching resources
end
LIMS -> GOMS : POST Transaction Bundle containing Task with new status \nand resource referenced via output
alt Success
GOMS -> GOMS : Create AuditEvent to track change \nand increment resource version
GOMS -> GOMS : Mark follow on Tasks as requested \n(if prerequisites are satisfied)
GOMS --> LIMS : Transaction Response Bundle containing updated resources
opt Event Notification if the update constitutes a final report
GOMS -> EPR : POST event-notification Bundle (report available)
end
else Failure
GOMS --> LIMS : Transaction Response Bundle containing OperationOutcomes with diagnostics
end
@enduml
</plantuml>

#### Update of Test Order

<plantuml>
@startuml
Participant EPR as "Requester (EPR)"
Participant GOMS as "Genomic Order Management Service Broker"
Participant LIMS as "Fulfilling Organization (GLH/LIMS)"
EPR -> GOMS : POST Transaction Bundle (including update to ServiceRequest\n and Provenance detailing change to ServiceRequest)
alt Success
GOMS -> GOMS : Updates to associated Tasks \n(e.g. on Order Cancellation)
GOMS --> EPR : Transaction Response Bundle containing updated resources
opt Event Notification
GOMS -> LIMS : POST event-notification Bundle (Test Order updated)
end
else Failure
GOMS --> EPR : Transaction Response Bundle containing OperationOutcomes with diagnostics
end
@enduml
</plantuml>

#### Update of Genomic Report

<plantuml>
@startuml
Participant EPR as "Requester (EPR)"
Participant GOMS as "Genomic Order Management Service Broker"
Participant LIMS as "Fulfilling Organization (GLH/LIMS)"
LIMS -> GOMS : POST Transaction Bundle (including update to DiagnosticReport\n and Provenance detailing change to report)
alt Success
GOMS --> LIMS : Transaction Response Bundle containing updated resources
opt Event Notification
GOMS -> EPR : POST event-notification Bundle (report updated)
end
else Failure
GOMS --> LIMS : Transaction Response Bundle containing OperationOutcomes with diagnostics
end
@enduml
</plantuml>

## Delete
It is not expected that delete operations will be supported by the central service for workflow based resources, e.g. if a service request or task was created in error. Cancellations or marking resources as entered in error SHOULD be represented using the associated status on the resources rather than deleting them from the central service to ensure auditability. However, if a clinical resource is no longer relevant, this may require a delete. Though additional logic will need to be added to the central service to ensure referential integrity and notifications if deletes constitute material changes affecting the processing of a test request. The Information Governance implications of limiting deletion of resources will be investigated within the Alpha phase of the project.