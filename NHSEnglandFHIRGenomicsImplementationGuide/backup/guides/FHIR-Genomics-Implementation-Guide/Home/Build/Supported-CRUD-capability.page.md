## {{page-title}}

Interactions supported by the API are defined within the {{pagelink:Home/FHIRAssets/CapabilityStatements/Instance.page.md}} CapabilityStatement. 

### Create
The main create operations will be creation of the initial test request and associated clinical information; creation of interim data (either binary files or structured FHIR resources attached to Task.output; and creation of the resulting DiagnosticReport resources. Creation of ServiceRequest and DiagnosticReport resources will trigger the associated processes to kick-off or close down a test order fulfilment workflow.

### Read
From initial design work, it is expected the main use case will be labs and requestors polling the central service for test orders and reports, including associated clinical information, as well as polling the system for the current state of Tasks and Task update history, through associated AuditEvents and Provenance resources.

### Update
A large part of the interactions with the central service, over the course of order fulfilment, will be updates to Task resources, which constitute status updates. These events will be captured by the central broker through AuditEvent resources. Additionally, ServiceRequest and DiagnosticReport resources may be updated if tests need to be changed or new data added, captured through Provenance resources. The impact these updates have on work-in-progress will be defined within Business Rules on the central broker (including how cancellations are managed).

### Delete
It is not expected that delete operations will be supported by the central service for workflow based resources, e.g. if a service request or task was created in error. Cancellations or marking resources as entered in error SHOULD be represented using the associated status on the resources rather than deleting them from the central service to ensure auditability. However, if a clinical resource is no longer relevant, this may require a delete. Though additional logic will need to be added to the central service to ensure referential integrity and notifications if deletes constitute material changes affecting the processing of a test request. The Information Governance implications of limiting deletion of resources will be investigated within the Alpha phase of the project.