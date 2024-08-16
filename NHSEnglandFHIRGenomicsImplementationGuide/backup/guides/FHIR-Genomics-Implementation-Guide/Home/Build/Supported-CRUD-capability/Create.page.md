## {{page-title}}

The main create operations will be creation of the initial test request and associated clinical information; creation of interim data (either binary files or structured FHIR resources attached to Task.output; and creation of the resulting DiagnosticReport resources. Creation of ServiceRequest and DiagnosticReport resources will trigger the associated processes to kick-off or close down a test order fulfilment workflow.

On create/POST, clients are allowed to not supply an 'id' within the resource, as per the FHIR spec. Any ids provided will be replaced by the central broker.

### Common Interaction Patterns

<plantuml>
@startuml
scale 0.8
== Creation of Test Order ==
Participant EPR as "Requester (EPR)"
Participant GOMS as "Genomic Order Management Service Broker"
Participant LIMS as "Fulfilling Organization (GLH/LIMS)"
EPR -> GOMS : POST Test Order Transaction Bundle
alt Success
GOMS -> GOMS : Create Tasks for Test Order
GOMS --> EPR : Transaction Response Bundle containing \ncreated resources
opt Event Notification
GOMS -> LIMS : POST event-notification Bundle \n(new tasks for org)
end
else Failure
GOMS --> EPR : Transaction Response Bundle containing \nOperationOutcomes with diagnostics
end
== Creation of Genomic Report ==
LIMS -> GOMS : POST Genomic Report Transaction Bundle
alt Success
GOMS --> LIMS : Transaction Response Bundle containing \ncreated resources
opt Event Notification
GOMS -> EPR : POST event-notification Bundle \n(report available)
end
else Failure
GOMS --> LIMS : Transaction Response Bundle containing \nOperationOutcomes with diagnostics
end
== Addition of Consent/RoD ==
EPR -> GOMS : POST Consent/ROD Transaction Bundle \n(including update to ServiceRequest.supportingInfo to \nreference Consent and Provenance detailing change to \nServiceRequest)
alt Success
GOMS --> EPR : Transaction Response Bundle containing \ncreated resources
opt Event Notification
GOMS -> LIMS : POST event-notification Bundle \n(Test Order updated)
end
else Failure
GOMS --> EPR : Transaction Response Bundle containing \nOperationOutcomes with diagnostics
end
== Addition of Specimen ==
alt Transaction
EPR -> GOMS : POST Specimen Transaction Bundle \n(including update to ServiceRequest.supportingInfo to reference \nSpecimen)
alt Success
GOMS -> GOMS : Addition of Specimen to relevant Tasks \n(could be performed manually)
GOMS --> EPR : Transaction Response Bundle containing \ncreated resources
opt Event Notification
GOMS -> LIMS : POST event-notification Bundle \n(Test Order updated)
end
else Failure
GOMS --> EPR : Transaction Response Bundle containing \nOperationOutcomes with diagnostics
end
else Single Resource
EPR -> GOMS : POST Specimen 
alt Success
GOMS --> EPR : Response with created resource
EPR -> GOMS : POST Transaction Bundle updating \nServiceRequest.supportingInfo and adding Provenance
alt Success
GOMS -> GOMS : Addition of Specimen to relevant Tasks \n(could be performed manually)
GOMS --> EPR : Transaction Response Bundle containing \ncreated resources
opt Event Notification
GOMS -> LIMS : POST event-notification Bundle \n(Test Order updated)
end
else Failure
GOMS --> EPR : Transaction Response Bundle containing \nOperationOutcomes with diagnostics
end
else Failure
GOMS --> EPR : OperationOutcome response with diagnostics
end
end
== Creation of new Task ==
LIMS -> GOMS : POST Task referencing ServiceRequest
alt Success
GOMS --> LIMS : Response with created resource
else Failure
GOMS --> LIMS : OperationOutcome response with diagnostics
end
@enduml
</plantuml>