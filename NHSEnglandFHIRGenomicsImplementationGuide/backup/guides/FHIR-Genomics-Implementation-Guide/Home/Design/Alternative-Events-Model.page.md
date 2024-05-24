## {{page-title}}

The mechanism for notifications, e.g. regarding test status updates, is still under review. 

The two main mechanisms for implementing Pub/Sub notification mechanisms are the National Events Management Service (NEMS) or native FHIR Subscriptions. 

NEMS is described in https://digital.nhs.uk/services/national-events-management-service
The FHIR Workflow approach is described on the {{pagelink:Interactions}} page, FHIR subscription event notifications are described within the [Subscriptions Backport IG](https://build.fhir.org/ig/HL7/fhir-subscription-backport-ig/)

## Publishing and receiving requirements
The Events model to be used is still under discussion. As such, no publishing and receiving requirements have yet been defined. 

This page will be updated with publishing and receiving requirements once the events model and system to be used have been finalised. 

In the final solution any updates to ServiceRequests are expected to trigger event notifications, through NEMS or otherwise, to requestors/GLHs, and vice versa for Task and DiagnosticReport updates.

## Task Notifications

### Pro-active Notification

For pro-active notification of task and test report creation or updates, where the test order service sends the Task and other resources to a receiving organisation/service, that receiving system SHALL also expose multiple API endpoints to enable that notification to be consumed. Alternative mechanisms such as use of messaging via MESH could be used to push notifications as messages rather than the receiving system needing to expose RESTful APIs.

Due to the short timescales for alpha delivery and possible technical immaturity of participating organisations, making exposing an API or processing a message over MESH challenging, initial alpha build will rely on polling to identify new and updated resources. Proactive notifications will be considered in later phases.

There are many options when it comes to pro-active notification, one or more of the below options could be implemented/integrated.

|Mechanism|Comment|
|--|--|
|National Events Management Service (NEMS)|NEMS implements a publish and subscribe pattern so would be ideal for organisations to receive tasks and updates. There are a few of significant blockers for use of the current NEMS service. - The NEMS service is currently using FHIR STU3, so is not compatible with the UK core resources which the test order system will use. - The service has a principle for light weight payloads where a pointer to where information can be retrieved is shared rather than the content, this would mean that a notification could be sent that a test has been created for an organisation, removing the need to poll, but would not stop a chatty interaction to get all the details about the task and referenced resources unlike if all the detail was sent with the message. - The onboarding, development & assurance of new event types can be lengthy and may not be achievable for the alpha.|
|Other national messaging services|There are a number of other services looking at a FHIR R4 messaging capability which supports publish and subscribe as well as other routing mechanisms. A proof of concept was implemented, but no production service has been created yet. This option will be reconsidered when pro-active notifications are being designed as a new messaging service would most likely implement a common authentication mechanism to that used by the test order service through API-M and would be being built and adopted by other services.|
|MESH|As the intended target of a task is known by the test order service it could directly forward the task data to the organisation using their ODS code and MESH. However, the future of the service is unknown, with a Multicast Notification Service (MNS) being proposed as a more extensible solution. MESH would allow the whole FHIR bundle to be shared so could be an efficient way of notifying a consumer of the information.|
|FHIR RESTful API calls|Connected systems could expose APIs for the service to POST resources to their system as a notification. To support the sending of new Tasks, Task updates and DiagnosticReports the services would have to implement the FHIR transaction interactions and the put interactions. They would not need to implement any of the read or search capabilities. There are a number of risks around this approach: - Managing send failures, deciding on retries and assessing the clinical risk if the information does not get to the target system. - API versioning, if the API is updated to include new elements or resources, if value sets are updated or code systems are added there is an increased risk that requests will be rejected if the target system has not implemented the update APIs.|
|NHS eMails|Utilising NHS email capabilities for notification|

### Poll Based Notification

For notification of Tasks and DiagnosticReports using a polling architecture, the receiving organisation/service needs to call the Test Order Service APIs to query for new or updated Tasks and/or DiagnosticReports, they will NOT need to expose APIs from their system. Different organisations will want to use different filters when querying the test order service, such as using their ODS code as the requester for search service request, the status of a DiagnosticReport to filter down to interim or final test reports etc.

One down side of polling for updates using the RESTful APIs is that the querying system may need to make subsequent requests to other APIs endpoints on the test order system to retrieve referenced resources, such as the Patient, PractitionerRole, ServiceRequest and Specimen, etc. The FHIR _include and _revinclude search parameters will be supported for some references which can be used to minimise the number of requests that are needed as this will allow referenced resources to be returned in the same bundle as the search results.

With polling there is a risk that the API would become a highly 'chatty' interaction between the systems, meaning more transactions, more processing time and more cost for both the central Test Order Service and consuming organisations/services, therefore, strategically, the pro-active notification is the preferred model, with polling as a backup capability where the connecting systems are not able to implement or expose an API from their systems.

The following are the key notification points:

|Notification Point|Reason|
|--|--|
|Creation of new Task resource|So organisations are informed of tasks they are being asked to perform|
|Update to Task resource|So organisations know when tasks they own or have involvement in have been updated or completed. This will include if the specimen or test is rejected|
|Creation of DiagnosticReport resource|To inform the requester/requesting EHR that the test has been completed and to share the DiagnosticReport|
|Update of DiagnosticReport resource|To inform the EHR that the DiagnosticReport has been updated|

For a user of the central service's proposed web portal, notifications would be triggered as the user session commences. In
most cases a poll based approach will be utilised to query into the central services and provide updates to users depending on the UI context.
