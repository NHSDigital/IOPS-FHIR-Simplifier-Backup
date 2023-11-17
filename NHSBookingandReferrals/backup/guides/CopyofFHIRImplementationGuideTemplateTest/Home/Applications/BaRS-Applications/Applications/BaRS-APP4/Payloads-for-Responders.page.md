---
topic: APP4-ResponderPayloads
---

# {{page-title}}
## Interim Validation Response Payload
This section provides guidance on the use of key resources, for the Responder to create an Interim Validation Response to return to the Requester. See [ServiceRequest - Response Validation Interim](https://simplifier.net/nhsbookingandreferrals/bars-messagedefinition-servicerequest-response-validation-interim) message definition for details of resources required for this payload.

_Note that Responders will also have to build the capability to receive and process the Validation Request and Cancellation payloads_
<br>

### MessageHeader Resource
For detailed information on the use of MessageHeader please refer to the {{pagelink:core-SPMessageHeader, text:Standard Pattern - Message Header}}. 

The MessageHeader resource in the Interim Validation Response should have the following resource elements set as follows:
* **MessageHeader.eventCoding** - **must** be populated with 'servicerequest-response'
* **MessageHeader.reasonCode** - **must** be 'new'
* **MessgeHeader.Response** - **must** be the original request BundleID

### ServiceRequest Resource
A key point when a Responder builds the Interim Validation Response 'message bundle' is to ensure the *MessageHeader.focus* references the new Encounter resource. When the request 'message bundle' is created by the Responder and processed by the Requester, this is the starting point from which the Interim Validation Request is understood. It provides either the detail or references to all key FHIR resources, for example, the Patient, new Encounter and Careplan. 

### Encounter Resource
The Encounter is used to represent the interaction between a patient and healthcare service provider. It links with numerous other resources, to reflect the activities performed in that encounter. 

In the Validation Request, the Requester will include an Encounter resource as the container for their assessment, which established the need for the Validation Request. 

In the Interim Validation Response a second Encounter resource is created by the Responder to represent the newly created case in their system, and is used to transfer the human readable case identifer. When acknowledging the receipt of a Validation Request, the Responder **must**:
* include a new, secondary, Encounter resource with the status of 'planned' in their response to the Requester. 
* The new encounter will have both an ID and an Identifier values, indicating the Responder's local reference and human readable one, respectively. 
* This second Encounter resource is the focus resource of the Interim Validation Response and the Validation Response
* *encounter.status* of 'in-progress' to be set on the second Encounter. This is to indicate to the Requester that the validation activity has started in the receiving service.
* *encounter.reasonCode* to be included on the second encounter to indicate that it is the validation triage outcome.

The human readable (Identifier) reference is a useful link for the services to use when discussing a patient's transition of care. The local (ID) reference is not intended to be human readable but rather machine readable. 
(See the {{pagelink:APP4-EntityRelationshipDiagrams, text:Entity Relationship Diagram}} for reference) 
<br>
<br>
<hr>

## Validation Response Payload
This section provides guidance on the use of key resources, for the Responder to create a Validation Response to return to the original Requester. See [ServiceRequest - Response Validation Full](https://simplifier.net/nhsbookingandreferrals/bars-messagedefinition-servicerequest-response-validation-full) message definition for details of resources required for this payload.

### MessageHeader Resource
For detailed information on the use of MessageHeader please refer to the {{pagelink:core-SPMessageHeader, text:Standard Pattern - Message Header}} for more information. 

The MessageHeader resource in the Interim Validation Response should have the following resource elements set as follows:
* **MessageHeader.eventCoding** - **must** be populated with 'servicerequest-response'
* **MessageHeader.reasonCode** - **must** be 'update' or 'new' if the Interim Validation Response was not sent
* **MessgeHeader.Response** - **must** be the original request BundleID

### ServiceRequest Resource
A key point when a Responder builds the Validation Response 'message bundle' is to ensure the *MessageHeader.focus* references the new Encounter resource. When the request 'message bundle' is created by the Responder and processed by the Requester, this is the starting point from which the Validation Request is understood. It provides either the detail or references to all key FHIR resources, for example, the Patient, new Encounter and Careplan.  

### Encounter Resource
The Encounter is used to represent the interaction between a patient and healthcare service provider. It links with numerous other resources, to reflect the activities performed in that encounter. 

In the Validation Request, the Requester will include an Encounter resource as the container for their assessment, which established the need for the Validation Request. 

In the Validation Response a second Encounter resource is created by the Responder to represent the newly created case in their system, and is used to transfer the human readable case identifer. When acknowledging the receipt of a Validation Request, the Responder **must**:
* include an *encounter.status* of 'finished' in their response to the Requester. This is to indicate to the Requester that the request has compeleted in the Responder system.
* The new encounter will have both an ID and an Identifier values, indicating the Responder's local reference and human readable one, respectively. 
* This second Encounter resource is the focus resource of the Interim Validation Response and the Validation Response
* *encounter.status* of 'in-progress' to be set on the second Encounter. This is to indicate to the Requester that the validation activity has started in the receiving service.
* *encounter.reasonCode* to be included on the second encounter to indicate that it is the validation triage outcome.

The human readable (Identifier) reference is a useful link for the services to use when discussing a patient's transition of care. The local (ID) reference is not intended to be human readable but rather machine readable. 
(See the {{pagelink:APP4-EntityRelationshipDiagrams, text:Entity Relationship Diagram}} for reference) 

A third Encounter **should** be included if a validation request has resulted in a higher ambulance category Cat1 or Cat2 where a Ambulance Request has been made to 999 AST via the original ITK route from a 111 service. The Requester **should** be able to see the ITK request and merge the new case with the case currently with the CAD on receipt of the Validation Response, using the identifiers provided on the ITK Ambulance Request. 

### Location Resource
The Location resource is used to transfer details of the incident location. Incident location details may change during the course of the assesment and any additional or modified location details will be captured in the Responder system. The new and updated location details should be sent in a validation response bundle. 

When a BARS Requester or Responder(in a response) populates the Location resource:

*  They **must** populate the *Location.extension* with at least one property or non-property element from the following:
    *  Unique Property Reference Number (UPRN)
    *  Postcode Address Finder (PAF) key
    *  Eastings/Northings
    *  what3words

*  They **should** populate the *Location.address* for all property based locations. 
*  They **should** populate *Location.address.line* which is a repeatable element, with the the order in which lines should appear in an address label
*  They **should** populate *Location.address.name* when there is a property name
*  They **should** populate *Location.address.text* with a text representation of the full address (including the address name), with each line separated by a comma

When a BARS Responder or the Requester(in a response) processes information in a Location resource:

*  They **should** consume and populate **all** address fields sent, into their system
*  They **must** display *all* address fields sent by the sender


### CarePlan Resource
The CarePlan resource is used in the Validation Response to communicate to the Requester a summary of what was ascertained during the validation consultation. 

The *CarePlan.status* is used to drive workflow on the Requesters system. This **must** be populated with either a value of ‘complete’ or 'active'. If the status is 'complete' the Requester will know there is no furthur action required. If the status is 'active' the Requester will know there is an action required following the validation.

The *careplan.activity* holds the assessment information, whether it be coded or free text. The *careplan.activity.outcomeCodeableConcept* is malleable enough to support the transmission of Pathways coded outcomes as well as clinical narrative. The element guidance for this resource below goes into the specific detail but, fundamentally, the Responder must include the following:
*  The Pathways, Symptom Group (SG),  Symptom Discriminator (SD) and Disposition (DX) codes, along with the Pathways consultation summary, or
*  Further clinical narrative, provided outside of Pathways assessment, can also be included under this element using 'text'
*  The Ambulance Response Programme (ARP) priority code

### Flag Resource
The Flag resource is used to communicate prospective warnings of potential issues when providing care to the patient. The Flag subject may be the Patient (e.g. Safeguarding concern) or the Location (e.g. Scene safety). The population of the Flag Resource is optional as not all subjects will have relevant issues.

BaRS Responder **should** populate Flag resources and **should** make adequate provision in their solution to support key flags in BaRS Application workflows, for example, Scene Safety, for this Application. When populating this resource, Responders **must** include both *flag.category* and *flag.code* values using the specific [BaRS CodeSystems](https://simplifier.net/nhsbookingandreferrals/~resources?category=CodeSystem&sortBy=DisplayName).

When a BARS Requester processes information in a Flag resource in a validation response;

* they **should** populate a flag in their system, if their solution supports that flag
* they **must** display the information in the Flag resource in a way that supports the associated workflow (i.e. the relevant end users can see it and act upon it)
* rendering of Flag information must be in line with the {{pagelink:principles_prerequesites, text:Principles for rendering BaRS Payload }}.

### Observation 
The Observation resource is used to carry assertions supporting the assessment performed by the Requester. Requesters **should** add clinical notes to the Careplan resource rather than Observation, especially where they expect a Responder to act upon the information. 

There are specific instances where an Observation **must** be used to convey information and [examples](https://simplifier.net/nhsbookingandreferrals/~resources?category=Example&exampletype=Observation&sortBy=DisplayName) are provided to aid development: 
* Where Birth Sex is communicated it **must** be transferred in a Validation Response using Observation. This information **should** only be transferred when considered clinically relevant and it is not considered as demographic information, as administrative gender would be. It **should <ins>not</ins>** be included as an extension on the patient resource, as described in [UK Core](https://simplifier.net/hl7fhirukcorer4/ukcorepatient). 
* Where Estimated Age is communicated it **must** be conveyed in an Observation.

### Consent 
The level of consent currently supported by BaRS is for 'Direct Care' only. In emergency care use cases this is usually implied consent. A Validation Response **must** contain a Consent resource and it **must** adhere to the [example](https://simplifier.net/NHSBookingandReferrals/8fc39b95-89a6-45fb-914f-1458a10e9e14/~json) provided under the BaRS FHIR assets. 
<br>
<br>
<hr>
<div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i>
    <b> Important:</b> 
    The sections below show elements in key resources that extend UK Core. Where no table is present, the basic UK Core resource is used unaltered.
</div>