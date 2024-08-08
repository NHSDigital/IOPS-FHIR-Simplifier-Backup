## {{page-title}}

A large part of the interactions with the central service, over the course of order fulfilment, will be updates to Task resources, which constitute status updates. These events will be captured by the central broker through AuditEvent resources. Additionally, ServiceRequest and DiagnosticReport resources may be updated if tests need to be changed or new data added. Reasons for changed SHOULD be captured through Provenance resources. The impact these updates have on work-in-progress will be defined within Business Rules on the central broker (including how cancellations are managed).

### Conditional Update
The conditional update interaction allows a client to update an existing resource based on some identification criteria, rather than by logical id. To accomplish this, the client issues a PUT with additional parameters to identify the resource to be updated, e.g. by identifier. 

Within the Alpha for Order Management, conditional updates will not be supported, i.e. it is expected that all updates will be submitted against a logical id. However, support for conditional updates will be investigated post-Alpha based on demand and use cases from users.

### Resource contention
To avoid 'Lost Updates', where two clients update the same resource, and the second overwrites the updates of the first, the If-Match header will be used. As per the [FHIR HTTP pages](https://hl7.org/fhir/R4/http.html#concurrency), servers SHOULD return an ETag header, matching the version id assigned by the server for the resource, when returning a resource (though the version id can be used directly).

Clients then SHOULD request a version aware update, when submitting PUTs by including an If-Match header that quotes the version id from the server:

```
PUT /Patient/347 HTTP/1.1
If-Match: W/"23"
```

If the version id given in the If-Match header does not match, the server SHOULD return a `412 Precondition Failed` status code instead of updating the resource.

Servers can require that clients provide an If-Match header by returning 400 Client Error status codes when no If-Match header is found. **Implementation of version specific updates for Genomic Order Management is pending development within the Alpha**

To support `If-Match` within Transaction Bundles, the Bundle.entry.request.ifMatch element SHOULD be used:

```json
"request": {
  "method": "PUT",
  "url": "Patient/347",
  "ifMatch": "W/\"23\""
}
```

### Patch 
As an alternative to updating an entire resource, some FHIR servers allow clients to perform a patch operation. This is useful for cases where only small changes are required to resources such as adding local identifiers. The patch interaction is performed by an HTTP PATCH command as shown:

`PATCH [base]/[type]/[id] {?_format=[mime-type]}`

The body of a PATCH operation SHALL be either:

a JSON Patch document with a content type of `application/json-patch+json`
an XML Patch document with a content type of `application/xml-patch+xml`
a FHIRPath Patch parameters resource with FHIR Content Type

**Implementation of the PATCH operation for Genomic Order Management will not be supported within the Alpha**

### Common Patterns

<plantuml>
@startuml
scale 0.8
== Update Task Status ==
Participant EPR as "Requester (EPR)"
Participant GOMS as "Genomic Order Management Service Broker"
Participant LIMS as "Fulfilling Organization (GLH/LIMS)"
Participant LIMS2 as "Sendaway Organization (remote GLH/LIMS)"
opt
LIMS -> GOMS : Search for Task to get ID 
GOMS --> LIMS : Searchset Bundle response with matching \nresources
end
LIMS -> GOMS : PUT Task with new \nstatus/businessStatus/input/output
alt Success
GOMS -> GOMS : Create AuditEvent to track change and \nincrement resource version
GOMS --> LIMS : Response with updated resource
else Failure
GOMS --> LIMS : OperationOutcome response with diagnostics \ne.g. unsupported state transition
end
== Reassign Task ==
opt
LIMS -> GOMS : Search for Task to get ID 
GOMS --> LIMS : Searchset Bundle response with matching \nresources
end
LIMS -> GOMS : PUT Task with new owner
alt Success
GOMS -> GOMS : Create AuditEvent to track change and \nincrement resource version
GOMS --> LIMS : Response with updated resource
alt Polling
LIMS2 -> GOMS : GET Task with owner=<ods_code>
GOMS --> LIMS2 : Searchset Bundle response with matching \nresources
else Event Notification
GOMS -> LIMS2 : POST event-notification Bundle \n(new tasks for org)
end
else Failure
GOMS --> LIMS : OperationOutcome response with diagnostics \ne.g. unsupported state transition
end
== Completion of Task with Output Reference ==
opt
LIMS -> GOMS : Search for Task to get ID 
GOMS --> LIMS : Searchset Bundle response with matching \nresources
end
LIMS -> GOMS : POST Transaction Bundle containing Task with \nnew status and resource referenced via output
alt Success
GOMS -> GOMS : Create AuditEvent to track change and \nincrement resource version
GOMS -> GOMS : Mark follow on Tasks as requested \n(if prerequisites are satisfied)
GOMS --> LIMS : Transaction Response Bundle containing \nupdated resources
opt Event Notification if the update constitutes a final \nreport
GOMS -> EPR : POST event-notification Bundle \n(report available)
end
else Failure
GOMS --> LIMS : Transaction Response Bundle containing \nOperationOutcomes with diagnostics
end
== Update of Test Order ==
EPR -> GOMS : POST Transaction Bundle \n(including update to ServiceRequest and \nProvenance detailing change to \nServiceRequest)
alt Success
GOMS -> GOMS : Updates to associated Tasks \n(e.g. on Order Cancellation)
GOMS --> EPR : Transaction Response Bundle containing \nupdated resources
opt Event Notification
GOMS -> LIMS : POST event-notification Bundle \n(Test Order updated)
end
else Failure
GOMS --> EPR : Transaction Response Bundle containing \nOperationOutcomes with diagnostics
end
== Update of Genomic Report ==
LIMS -> GOMS : POST Transaction Bundle \n(including update to DiagnosticReport and \nProvenance detailing change to \nreport)
alt Success
GOMS --> LIMS : Transaction Response Bundle containing \nupdated resources
opt Event Notification
GOMS -> EPR : POST event-notification Bundle \n(report updated)
end
else Failure
GOMS --> LIMS : Transaction Response Bundle containing \nOperationOutcomes with diagnostics
end
@enduml
</plantuml>