# {{page-title}}

Interactions supported by the API are defined within the {{pagelink:Home/FHIRAssets/CapabilityStatements/Instance.page.md}} CapabilityStatement. 

Expected patterns for responses based on Transaction vs. Individual Resource, HTTP Verbs used and Success vs. Failure are detailed in {{pagelink:acknowledgementsandresponses}}.

## Create
The main create operations will be creation of the initial test request and associated clinical information; creation of interim data (either binary files or structured FHIR resources attached to Task.output; and creation of the resulting DiagnosticReport resources. Creation of ServiceRequest and DiagnosticReport resources will trigger the associated processes to kick-off or close down a test order fulfilment workflow.

### Common Interaction Patterns

<plantuml>
@startuml
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

## Read
From initial design work, it is expected the main use case will be labs and requestors polling the central service for test orders and reports, including associated clinical information, as well as polling the system for the current state of Tasks and Task update history, through associated AuditEvents and Provenance resources. 

Retrieval of sets of resources using {{pagelink:Home/FHIRAssets/GraphDefinitions}} are also planned. The complete set of resources/operations supported are listed within the {{pagelink:Home/FHIRAssets/CapabilityStatements/Instance.page.md}} page. All resources are expected to be compliant with UK Core FHIR R4.

### Search

#### Supported Functionality
* The search parameters to be supported by the Genomic Order Management system are defined within the {{pagelink:Home/FHIRAssets/CapabilityStatements/Instance.page.md}} page. Custom search parameters defined within {{pagelink:Home/FHIRAssets/SearchParameters}} will also be supported, such as a search parameter for supporting retrieval of supporting-info on ServiceRequests. 

* Multiple _include/_revinclude parameters will be supported within a single URL search string. The :iterate modifier will also be supported to enable traversal of multiple levels of references in searches e.g. `GET [base]/MedicationDispense?_include=Medication:prescription&_include:iterate=MedicationRequest:requester&criteria...`. 

* The `_history` and `_lastUpdated` parameters will be supported as part of history and audit provenance needs. The `_history` parameter will only be supported on instance level reads, i.e. history will not be retrievable at the resource type or base levels.

* Token type searching for coded values based on system and/or code e.g. http://snomed.info/sct%7C3738000 will be supported, to enable unabiguous searching of codes.

* Date and number based prefixes, such as `eq`, `gr`, `lt` will be supported, to enable retrieval of resources based on date/time and quantity ranges.

* Chaining, e.g. `ServiceRequest?subject:Patient.name` will be supported to aid building of complex search criteria.

* Search result modifiers such as `_count`, `_total` and `_sort` will be supported to allow clients to tailor search results.

* The `:not` operator will be supported to allow organizations visibility of tests outside their region, e.g. for home GLHs which want to see tests from within their patch routed to labs outside their region. An example of the query to support this would be:

```
GET [base]/ServiceRequest?requester:PractitionerRole.organization={ODS_codes_in_my_patch}&performer:not={my_GLH_code}
```

#### Unsupported Functionality
* Inclusion of external references (resources not hosted on the server) through the _include parameter will not be supported as there will be no guarantee they resolve or that they will return valid FHIR. While this may mean clients will need to perform multiple calls to construct a complete set of data, this ensures consistency of the responses from the broker. Within this Implementation Guide we expect test requesters to submit all relevant information for a test order to the broker so there should be very few instances where an external reference is used.

* No use cases requiring use of `_query` or `$operation` type searches have been elaborated so these are not planned to be supported as of the time of publication. Equally, usage of tags to encode data, and use of the `_tag` parameter will not be supported until use cases detailing their need are elaborated.

* Search modifiers such as `:contains`, `:missing`, `:not-in`, etc. will not be supported as there are currently no use cases for supporting text-based/fuzzy searching. 

### Common Patterns

<plantuml>
@startuml
== Searching for Tasks by Org (Polling for tasks) ==
Participant EPR as "Requester (EPR)"
Participant GOMS as "Genomic Order Management Service Broker"
Participant LIMS as "Fulfilling Organization (GLH/LIMS)"
alt Only matching resources
LIMS -> GOMS : GET Task with owner=<ods_code> 
GOMS --> LIMS : Searchset Bundle response with matching \nresources
else Additional includes
LIMS -> GOMS : GET Task with owner=<ods_code> and \n_include=Task:focus
GOMS --> LIMS : Searchset Bundle response with matching \nresources and included referenced ServiceRequests
end
== Searching for ServiceRequest by Patient ==
LIMS -> GOMS : GET ServiceRequest with subject=<nhs_number> 
GOMS --> LIMS : Searchset Bundle response with matching \nresources
== Retrieving Test Orders ==
opt
LIMS -> GOMS : Search for ServiceRequest to get ID 
end
LIMS -> GOMS : GET ServiceRequest/<id>/ with \n$graph?graph=genomics-test-order 
GOMS --> LIMS : Collection Bundle response with resources \nreferenced in the graph
== Retrieving DiagnosticReport by ID ==
alt Using report endpoint
EPR -> GOMS : Search for DiagnosticReport to get ID 
else Using task endpoint
EPR -> GOMS : Search for Tasks with focus=ServiceRequest
EPR -> EPR : Parse link in Task.output to get ID
end
alt Unstructured Report
EPR -> GOMS : GET DiagnosticReport using ID
GOMS --> EPR : DiagnosticReport
EPR -> EPR : Follow link to retrieve PDF \nor decode base65 encoded data
else Structured Reports
EPR -> GOMS : GET DiagnosticReport/<id>/ \n with $graph?graph=genomics-result 
GOMS --> EPR : Collection Bundle response with resources \nreferenced in the graph
end
@enduml
</plantuml>

## Update
A large part of the interactions with the central service, over the course of order fulfilment, will be updates to Task resources, which constitute status updates. These events will be captured by the central broker through AuditEvent resources. Additionally, ServiceRequest and DiagnosticReport resources may be updated if tests need to be changed or new data added. Reasons for changed SHOULD be captured through Provenance resources. The impact these updates have on work-in-progress will be defined within Business Rules on the central broker (including how cancellations are managed).

### Conditional Update
The conditional update interaction allows a client to update an existing resource based on some identification criteria, rather than by logical id. To accomplish this, the client issues a PUT with additional parameters to identify the resource to be updated, e.g. by identifier. 

For the Order Management Alpha, conditional updates will not be supported, i.e. it is expected that all updates will be submitted against a logical id. However, support for conditional updates will be investigated post-Alpha based on demand and use cases from users.

### Resource contention
To avoid 'Lost Updates', where two clients update the same resource, and the second overwrites the updates of the first, the If-Match header will be used. As per the [FHIR HTTP pages](https://hl7.org/fhir/R4/http.html#concurrency), servers SHOULD return an ETag header, matching the version id assigned by the server for the resource, when returning a resource (though the version id can be used directly).

Clients then SHOULD request a version aware update, when submitting PUTs by including an If-Match header that quotes the version id from the server:

```
PUT /Patient/347 HTTP/1.1
If-Match: W/"23"
```

If the version id given in the If-Match header does not match, the server SHOULD return a `412 Precondition Failed` status code instead of updating the resource.

Servers can require that clients provide an If-Match header by returning 400 Client Error status codes when no If-Match header is found. **Implementation of version specific updates for Genomic Order Management is pending internal review**

### Patch 
As an alternative to updating an entire resource, some FHIR servers allow clients to perform a patch operation. This is useful for cases where only small changes are required to resources such as adding local identifiers. The patch interaction is performed by an HTTP PATCH command as shown:

`PATCH [base]/[type]/[id] {?_format=[mime-type]}`

The body of a PATCH operation SHALL be either:

a JSON Patch document with a content type of `application/json-patch+json`
an XML Patch document with a content type of `application/xml-patch+xml`
a FHIRPath Patch parameters resource with FHIR Content Type

**Implementation of the PATCH operation for Genomic Order Management is pending internal review**

### Common Patterns

<plantuml>
@startuml
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

## Delete
It is not expected that delete operations will be supported by the central service for workflow based resources, e.g. if a service request or task was created in error. Cancellations or marking resources as entered in error SHOULD be represented using the associated status on the resources rather than deleting them from the central service to ensure auditability. However, if a clinical resource is no longer relevant, this may require a delete. Though additional logic will need to be added to the central service to ensure referential integrity and notifications if deletes constitute material changes affecting the processing of a test request. The Information Governance implications of limiting deletion of resources will be investigated within the Alpha phase of the project.