## {{page-title}}

Although some workflow interactions are structured/digital particularly the initial request (referral, test request, etc).  The subsequent events and sub tasks are predominantly SMS and Email based with the recipient manually updating their computer systems.

{{render:diagrams-TechnicalFramework-Workflow-TextCommunication}}

Workflow Events replace the email/SMS interaction with simple structured interactions which is centred around the practitioner/patient requirements to communicate around workflow. 

This is roughly the same as Resource, Message and Document notifications discussed previously. The terminology has changed to reflect patient and practitioner focus:

- Resource / Document Source has become Placer, who is the person making the request.
- Resource / Document Consumer has become filler, who is the person fulfilling the request. 

{{render:diagrams-TechnicalFramework-Workflow-WorkflowCommunication}}

In [FHIR Workflow](https://hl7.org/fhir/R4/workflow.html) these notifications use the FHIR Task resource. Email/SMS are/can still present and they will supplement the structured Placer and Filler interactions.  

{{render:diagrams-TechnicalFramework-Workflow-WorkflowCommunicationExample}}

TODO Add in more details on FHIR Task

### FHIR Task and Coding State Changes

Both the SNOMED CT coding and FHIR Task involve the communication of state changes between providers. The FHIR Workflow diagram illustrates a high-level view of the state changes.

{{render:diagrams-TechnicalFramework-Workflow-event-state-machine}}

From a technical perspective FHIR Task is being used here as a both a [Request](https://hl7.org/fhir/R4/workflow.html#request) and an [Event](https://hl7.org/fhir/R4/workflow.html#event) 
