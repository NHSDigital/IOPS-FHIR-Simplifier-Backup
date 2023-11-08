---
topic: APP4-Payloads
---


## {{page-title}}
## Validation Request Payload
The below details the specific guidance around the use of resources required to create a validation request by the referral sender. See [ServiceRequest - Request Validation](https://simplifier.net/nhsbookingandreferrals/messagedefinition-bars-messagedefinition-servicerequest-request-validation) message definition for details.

### MessageHeader Resource
The MessageHeader resource is required as part of the technical capability of making a request or response. Rather than providing clinical or administrative content for the end users; the function of all other resources are outlined. This resource holds key information about where the request has come from (*MessageHeader.source*), who it is intended for (*MessageHeader.destination*), what type of request it is (*MessageHeader.eventCoding*) and how to start interpreting the request (*MessageHeader.focus*). 

Any Receiver of the request 'message bundle' **must** first check the *MessageHeader.destination* and verify the *MessageHeader.destination.receiver.reference* refers to their Organisation. The *MessageHeader.destination.endpoint* is, in turn, the Healthcare Service ID they are expected to be processing the request on behalf of. 

The type of request **must** be checked next and there are three important elements which drive workflow: 
* **eventCoding** - determines the type of request. The value **must** be populated from this [CodeSystem](https://simplifier.net/NHSBookingandReferrals/message-events-bars) and will always be referral for this Application.
* **reasonCode** - indicates whether the message is new or an update to something the Receiver already has. The value **must** be populated from this [CodeSystem](https://simplifier.net/NHSBookingandReferrals/message-reason-bars).
* **definition** - specifies the [MessageDefinition](https://simplifier.net/nhsbookingandreferrals/~resources?category=Example&exampletype=MessageDefinition&sortBy=DisplayName) the request **must** adhere to and **must** be rejected if it fails to do so.

Once the above checks have been made the detail of the request can start to be unpacked and processed. The *MessageHeader.focus* provides the key to doing this. It indicates the lens through which the request 'message bundle' **must** be interpreted. In this Application the element will always point to the ServiceRequest. Most other FHIR resources in the 'message bundle' will link to or from the 'focus' resource. 

When generating asynchronous Response messages (as opposed to an HTTP synchronous response (200) message), where a Receiver is sending a 'message bundle' back to an originating Sender. Firstly, the Sender, in the original request **must** include a NHSD-Target-Identifier (their reference on the Endpoint Catalogue) under *MessageHeader.source.endpoint*, to which the Receiver is able to direct a response back to, regardless of whether they expect a response or not. The Receiver **must** take and store this value, along with the *Bundle.Id* value, to send a response message back to the Sender through the BaRS API Proxy. 

The workflow dictates an asynchronous response is to be sent, the Receiver **must** populate *MessageHeader.response.identifier* with the *Bundle.Id* of the original request 'message bundle' and set the *MessageHeader.response.code* value to 'ok'. 

### ServiceRequest Resource
The 'focus' resource in a referral is the ServiceRequest resource. When the request 'message bundle' is created by the Sender and processed by the Receiver, this is the starting point from which the referral is understood. It provides either the detail or references to all key FHIR resources, for example, the Patient, Encounter and Careplan. The guidance for this resource below provides more granular, element level, detail. A key point when a Sender builds the referral FHIR 'message bundle' is to ensure the *MessageHeader.focus* references the ServiceRequest resource.

Additionally, the *ServiceRequest.occurrencePeriod* **must** be populated with the time that the receiving service must contact the patient by (validation breach time)

### Encounter Resource
The Encounter is used to represent the interaction between a patient and healthcare service provider. It links with numerous other resources, to reflect the assessment performed. 

In the initial referral request, the Sender will include an Encounter resource as the container for their assessment, which established the need for the referral. This encounter **should** include a reference to the Sender's assessment under *encounter.identifier*. Additionally, the *encounter.episodeOfCare* **must** be populated with a 'Journey ID' reference which can be used in subsequent referrals to allow the audit of the route a patient took through service providers to resolve their initial request for care. 

A second Encounter resource is used to transfer the human readable reference of the newly created referral, at the Receiver side. When a referral request is made, the Receiver **should** include a new, secondary, encounter resource with the status of 'planned' in their synchronous HTTP response (200) to the Sender's request. This new 'planned' encounter will have both an Id and an Identifier value, indicating the Receiver's local reference and human readable one, respectively. (See the {{pagelink:APP3-EntityRelationshipDiagrams, text:Entity Relationship Diagram}} for reference). The human readable (Identifier) reference is a useful link for the services to use when discussing a patient's transition of care. The local (Id) reference is not intended to be human readable but rather machine readable.

### Location Resource ###
The Location resource is used to transfer details of the incident location.

When a BARS Sender populates the Location resource:

*  They **must** populate the *Location.extension* with at least one property or non-property element from the following:
    *  Unique Property Reference Number (UPRN)
    *  Postcode Address Finder (PAF) key
    *  Eastings/Northings
    *  what3words

*  They **should** populate the *Location.address* for all property based locations. 
*  They **should** populate *Location.address.line* which is a repeatable element, with the the order in which lines should appear in an address label
*  They **should** populate *Location.address.name* when there is a property name
*  They **should** populate *Location.address.text* with a text representation of the full address (including the address name), with each line separated by a comma

When a BARS Receiver processes information in a Location resource:

*  They **should** consume and populate **all** address fields sent, into their system
*  They **must** display *all* address fields sent by the Sender


### CarePlan Resource
The CarePlan resource is used in a referral request to communicate the 999 AST triage outcome and any associated clinical information, based on the assessment performed by the Sender. The Receiver will utilise the detail in this resource to summarise what the previous assessment ascertained about the patient, to be used in any subsequent consultation with the patient.

Primarily, *careplan.activity* is the section which holds this information, whether it be coded or free text. The *careplan.activity.outcomeCodeableConcept* is malleable enough to support the transmission of AMPDS and Pathways coded outcomes as well as clinical narrative. The element guidance for this resource below goes into the specific detail but, fundamentally, the Sender must include the following:
*  The selected AMPDS dispatch code and triage summary, or  
*  The Pathways, Symptom Group (SG),  Symptom Discriminator (SD) and Disposition (DX) codes, along with the Pathways consultation summary. 
*  Further clinical narrative, provided outside of the AMPDS or Pathways assessment, can also be included under this element using 'text'
*  The Ambulance Response Programme (ARP) priority code

### Flag Resource
The Flag resource is used to communicate prospective warnings of potential issues when providing care to the patient. The Flag subject may be the Patient (e.g. Safeguarding concern) or the Location (e.g. Scene safety). The population of the Flag Resource is optional as not all subjects will have relevant issues.

BaRS Senders **should** populate Flag resources and **should** make adequate provision in their solution to support key flags in BaRS Application workflows, for example, Scene Safety, for this Application. When populating this resource, Senders **must** include both *flag.category* and *flag.code* values using the specific [BaRS CodeSystems](https://simplifier.net/nhsbookingandreferrals/~resources?category=CodeSystem&sortBy=DisplayName).

When a BARS Receiver processes information in a Flag resource;

* they **should** populate a flag in their system, if their solution supports that flag
* they **must** display the information in the Flag resource in a way that supports the associated workflow (i.e. the relevant end users can see it and act upon it)
* rendering of Flag information must be in line with the {{pagelink:principles_prerequesites, text:Principles for rendering BaRS Payload }}.

### Observation 
The Observation resource is used to carry assertions supporting the assessment performed by the Sender. Senders **should** add clinical notes to the Careplan resource rather than Observation, especially where they expect a Receiver to act upon the information. 

There are specific instances where an Observation **must** be used to convey information and [examples](https://simplifier.net/nhsbookingandreferrals/~resources?category=Example&exampletype=Observation&sortBy=DisplayName) are provided to aid development: 
* Where Birth Sex is communicated it **must** be transferred in a referral using Observation. This information **should** only be transferred when considered clinically relevant and it is not considered as demographic information, as administrative gender would be. It **should <ins>not</ins>** be included as an extension on the patient resource, as described in [UK Core](https://simplifier.net/hl7fhirukcorer4/ukcorepatient). 
* Where Estimated Age is communicated it **must** be conveyed in an Observation.

### Consent 
The level of consent currently supported by BaRS is for 'Direct Care' only. In emergency care use cases this is usually implied consent. A referral **must** contain a Consent resource and it **must** adhere to the [example](https://simplifier.net/NHSBookingandReferrals/8fc39b95-89a6-45fb-914f-1458a10e9e14/~json) provided under the BaRS FHIR assets. 
<br>
<br>
<hr>

## Validation Interim Response Payload
The below details the specific guidance around the use of key resources required to create a validation response by the referral receiver to the original referral sender. See [ServiceRequest - Response Validation Interim](https://simplifier.net/nhsbookingandreferrals/bars-messagedefinition-servicerequest-response-validation-interim) message definition for details.
<br>

### MessageHeader Resource
The MessageHeader resource is required as part of the technical capability of making a request or response. Rather than providing clinical or administrative content for the end users; the function of all other resources are outlined. This resource holds key information about where the request has come from (*MessageHeader.source*), who it is intended for (*MessageHeader.destination*), what type of request it is (*MessageHeader.eventCoding*) and how to start interpreting the request (*MessageHeader.focus*). 

Any Receiver of the request 'message bundle' **must** first check the *MessageHeader.destination* and verify the *MessageHeader.destination.receiver.reference* refers to their Organisation. The *MessageHeader.destination.endpoint* is, in turn, the Healthcare Service ID they are expected to be processing the request on behalf of. 

The type of request **must** be checked next and there are three important elements which drive workflow: 
* **eventCoding** - determines the type of request. The value **must** be populated from this [CodeSystem](https://simplifier.net/NHSBookingandReferrals/message-events-bars) and will always be referral for this Application.
* **reasonCode** - indicates whether the message is new or an update to something the Sender already has. The value **must** be populated from this [CodeSystem](https://simplifier.net/NHSBookingandReferrals/message-reason-bars).
* **definition** - specifies the [MessageDefinition](https://simplifier.net/nhsbookingandreferrals/~resources?category=Example&exampletype=MessageDefinition&sortBy=DisplayName) the request **must** adhere to and **must** be rejected if it fails to do so.

Once the above checks have been made the detail of the request can start to be unpacked and processed. The *MessageHeader.focus* provides the key to doing this. It indicates the lens through which the request 'message bundle' **must** be interpreted. In this Application the element will always point to the ServiceRequest. Most other FHIR resources in the 'message bundle' will link to or from the 'focus' resource. 

When generating asynchronous (Interim or Final) Response messages (as opposed to an HTTP synchronous response (200) message), where a Receiver is sending a 'message bundle' back to an originating Sender. Firstly, the Sender, in the original request **must** include a NHSD-Target-Identifier (their reference on the Endpoint Catalogue) under *MessageHeader.source.endpoint*, to which the Receiver is able to direct a response back to, regardless of whether they expect a response or not. The Receiver **must** take and store this value, along with the *Bundle.Id* value, to send a response message back to the Sender through the BaRS API Proxy. 

The workflow dictates an asynchronous response is to be sent, the Receiver **must** populate *MessageHeader.response.identifier* with the *Bundle.Id* of the original request 'message bundle' and set the *MessageHeader.response.code* value to 'ok'. 

### ServiceRequest Resource
The 'focus' resource in a referral is the ServiceRequest resource. When the request 'message bundle' is created by the Sender and processed by the Receiver, this is the starting point from which the referral is understood. It provides either the detail or references to all key FHIR resources, for example, the Patient, Encounter and Careplan. The guidance for this resource below provides more granular, element level, detail. A key point when a Receiver builds the referral FHIR response 'message bundle' is to ensure the *MessageHeader.focus* references the ServiceRequest resource.

Additionally, the *ServiceRequest.occurrencePeriod* **must** be populated with the time that the receiving service must contact the patient by (validation breach time), this is a echo from the original request.

### Encounter Resource
The Encounter is used to represent the interaction between a patient and healthcare service provider. It links with numerous other resources, to reflect the assessment performed. 

In the initial referral request, the Sender will include an Encounter resource as the container for their assessment, which established the need for the referral. This encounter **should** include a reference to the Sender's assessment under *encounter.identifier*. Additionally, the *encounter.episodeOfCare* **must** be populated with a 'Journey ID' reference which can be used in subsequent referrals to allow the audit of the route a patient took through service providers to resolve their initial request for care. 

A second Encounter resource is used to transfer the human readable reference of the newly created referral, at the Receiver side. When a referral request is made, the Receiver **should** include a new, secondary, encounter resource with the status of 'planned' in their synchronous HTTP response (200) to the Sender's request. This new 'planned' encounter will have both an Id and an Identifier value, indicating the Receiver's local reference and human readable one, respectively. (See the {{pagelink:APP3-EntityRelationshipDiagrams, text:Entity Relationship Diagram}} for reference). The human readable (Identifier) reference is a useful link for the services to use when discussing a patient's transition of care. The local (Id) reference is not intended to be human readable but rather machine readable.

When the interim response is sent an *encounter.status* of 'in-progress' **must** be set on the second Encounter. This is to indicate to the Sender that the request has started in the receiving service.
The *encounter.reasonCode* **must** be included on the second encounter to indicate that it is the validation triage outcome. 
<br>
<br>
<hr>

## Validation Final Response Payload
The below details the specific guidance around the use of key resources required to create a validation response by the referral receiver to the original referral sender. See [ServiceRequest - Response Validation Full](https://simplifier.net/nhsbookingandreferrals/bars-messagedefinition-servicerequest-response-validation-full) message definition for details.

### MessageHeader Resource
The MessageHeader resource is required as part of the technical capability of making a request or response. Rather than providing clinical or administrative content for the end users; the function of all other resources are outlined. This resource holds key information about where the request has come from (*MessageHeader.source*), who it is intended for (*MessageHeader.destination*), what type of request it is (*MessageHeader.eventCoding*) and how to start interpreting the request (*MessageHeader.focus*). 

Any Receiver of the request 'message bundle' **must** first check the *MessageHeader.destination* and verify the *MessageHeader.destination.receiver.reference* refers to their Organisation. The *MessageHeader.destination.endpoint* is, in turn, the Healthcare Service ID they are expected to be processing the request on behalf of. 

The type of request **must** be checked next and there are three important elements which drive workflow: 
* **eventCoding** - determines the type of request. The value **must** be populated from this [CodeSystem](https://simplifier.net/NHSBookingandReferrals/message-events-bars) and will always be referral for this Application.
* **reasonCode** - indicates whether the message is new or an update to something the Sender already has. The value **must** be populated from this [CodeSystem](https://simplifier.net/NHSBookingandReferrals/message-reason-bars).
* **definition** - specifies the [MessageDefinition](https://simplifier.net/nhsbookingandreferrals/~resources?category=Example&exampletype=MessageDefinition&sortBy=DisplayName) the request **must** adhere to and **must** be rejected if it fails to do so.

Once the above checks have been made the detail of the request can start to be unpacked and processed. The *MessageHeader.focus* provides the key to doing this. It indicates the lens through which the request 'message bundle' **must** be interpreted. In this Application the element will always point to the ServiceRequest. Most other FHIR resources in the 'message bundle' will link to or from the 'focus' resource. 

When generating asynchronous (Interim or Final) Response messages (as opposed to an HTTP synchronous response (200) message), where a Receiver is sending a 'message bundle' back to an originating Sender. Firstly, the Sender, in the original request **must** include a NHSD-Target-Identifier (their reference on the Endpoint Catalogue) under *MessageHeader.source.endpoint*, to which the Receiver is able to direct a response back to, regardless of whether they expect a response or not. The Receiver **must** take and store this value, along with the *Bundle.Id* value, to send a response message back to the Sender through the BaRS API Proxy. 

The workflow dictates an asynchronous response is to be sent, the Receiver **must** populate *MessageHeader.response.identifier* with the *Bundle.Id* of the original request 'message bundle' and set the *MessageHeader.response.code* value to 'ok'. 

### ServiceRequest Resource
The 'focus' resource in a referral is the ServiceRequest resource. When the request 'message bundle' is created by the Sender and processed by the Receiver, this is the starting point from which the referral is understood. It provides either the detail or references to all key FHIR resources, for example, the Patient, Encounter and Careplan. The guidance for this resource below provides more granular, element level, detail. A key point when a Receiver builds the referral FHIR response 'message bundle' is to ensure the *MessageHeader.focus* references the ServiceRequest resource.

Additionally, the *ServiceRequest.occurrencePeriod* **must** be populated with the time that the receiving service must contact the patient by (validation breach time), this is a echo from the original request. 

### Encounter Resource
The Encounter is used to represent the interaction between a patient and healthcare service provider. It links with numerous other resources, to reflect the assessment performed. 

In the initial referral request, the Sender will include an Encounter resource as the container for their assessment, which established the need for the referral. This encounter **should** include a reference to the Sender's assessment under *encounter.identifier*. Additionally, the *encounter.episodeOfCare* **must** be populated with a 'Journey ID' reference which can be used in subsequent referrals to allow the audit of the route a patient took through service providers to resolve their initial request for care. 

A second Encounter resource is used to transfer the human readable reference of the newly created referral, at the Receiver side. When a referral request is made, the Receiver **should** include a new, secondary, encounter resource with the status of 'planned' in their synchronous HTTP response (200) to the Sender's request. This new 'planned' encounter will have both an Id and an Identifier value, indicating the Receiver's local reference and human readable one, respectively. (See the {{pagelink:APP3-EntityRelationshipDiagrams, text:Entity Relationship Diagram}} for reference). The human readable (Identifier) reference is a useful link for the services to use when discussing a patient's transition of care. The local (Id) reference is not intended to be human readable but rather machine readable.

When the final response is sent an *encounter.status* of 'finished' or 'triaged' **must** be set on the second Encounter. This is to indicate to the Sender that the request has compeleted in the receiving system. The *encounter.reasonCode* **must** be included on the second encounter to indicate that it is the validation triage outcome. 

A third Encounter **should** be included if a validation request has resulted in a higher ambulance category  Cat1 or Cat2 where a request has been made to 999 AST via the original ITK route from a 111 service via an automated Ambulance Request ITK. The Sender **should** be able to see the ITK request and merge the new case with the case currently with the CAS on receipt of the final message using the identifiers provided on the Ambulance Request. 

### Location Resource ###
The Location resource is used to transfer details of the incident location.

When a BARS Sender populates the Location resource:

*  They **must** populate the *Location.extension* with at least one property or non-property element from the following:
    *  Unique Property Reference Number (UPRN)
    *  Postcode Address Finder (PAF) key
    *  Eastings/Northings
    *  what3words

*  They **should** populate the *Location.address* for all property based locations. 
*  They **should** populate *Location.address.line* which is a repeatable element, with the the order in which lines should appear in an address label
*  They **should** populate *Location.address.name* when there is a property name
*  They **should** populate *Location.address.text* with a text representation of the full address (including the address name), with each line separated by a comma

When a BARS Receiver processes information in a Location resource:

*  They **should** consume and populate **all** address fields sent, into their system
*  They **must** display *all* address fields sent by the Sender


### CarePlan Resource
The CarePlan resource is used in a referral request to communicate the 999 AST triage outcome and any associated clinical information, based on the assessment performed by the Sender. The Receiver will utilise the detail in this resource to summarise what the previous assessment ascertained about the patient, to be used in any subsequent consultation with the patient.

The CarePlan resource is used in the validation response to communicate to the original Sender a summary of what was ascertained during the validation consultation. 

*CarePlan.status* is used to drive workflow on the original Sender system. This **must** be populated with the value ‘complete’ or 'active'. If a status is 'complete' the Sender will know there is no furthur action required. If the status is 'active' they will need to action the case following a validation.

*careplan.activity* holds the assessment information, whether it be coded or free text. The *careplan.activity.outcomeCodeableConcept* is malleable enough to support the transmission of Pathways coded outcomes as well as clinical narrative. The element guidance for this resource below goes into the specific detail but, fundamentally, the Receiver must include the following:
*  The Pathways, Symptom Group (SG),  Symptom Discriminator (SD) and Disposition (DX) codes, along with the Pathways consultation summary, or
*  Further clinical narrative, provided outside of Pathways assessment, can also be included under this element using 'text'
*  The Ambulance Response Programme (ARP) priority code

### Flag Resource
The Flag resource is used to communicate prospective warnings of potential issues when providing care to the patient. The Flag subject may be the Patient (e.g. Safeguarding concern) or the Location (e.g. Scene safety). The population of the Flag Resource is optional as not all subjects will have relevant issues.

BaRS Receiver **should** populate Flag resources and **should** make adequate provision in their solution to support key flags in BaRS Application workflows, for example, Scene Safety, for this Application. When populating this resource, Receivers **must** include both *flag.category* and *flag.code* values using the specific [BaRS CodeSystems](https://simplifier.net/nhsbookingandreferrals/~resources?category=CodeSystem&sortBy=DisplayName).

When a BARS Sender processes information in a Flag resource in a validation response;

* they **should** populate a flag in their system, if their solution supports that flag
* they **must** display the information in the Flag resource in a way that supports the associated workflow (i.e. the relevant end users can see it and act upon it)
* rendering of Flag information must be in line with the {{pagelink:principles_prerequesites, text:Principles for rendering BaRS Payload }}.

### Observation 
The Observation resource is used to carry assertions supporting the assessment performed by the Sender. Senders **should** add clinical notes to the Careplan resource rather than Observation, especially where they expect a Receiver to act upon the information. 

There are specific instances where an Observation **must** be used to convey information and [examples](https://simplifier.net/nhsbookingandreferrals/~resources?category=Example&exampletype=Observation&sortBy=DisplayName) are provided to aid development: 
* Where Birth Sex is communicated it **must** be transferred in a referral using Observation. This information **should** only be transferred when considered clinically relevant and it is not considered as demographic information, as administrative gender would be. It **should <ins>not</ins>** be included as an extension on the patient resource, as described in [UK Core](https://simplifier.net/hl7fhirukcorer4/ukcorepatient). 
* Where Estimated Age is communicated it **must** be conveyed in an Observation.

### Consent 
The level of consent currently supported by BaRS is for 'Direct Care' only. In emergency care use cases this is usually implied consent. A referral **must** contain a Consent resource and it **must** adhere to the [example](https://simplifier.net/NHSBookingandReferrals/8fc39b95-89a6-45fb-914f-1458a10e9e14/~json) provided under the BaRS FHIR assets. 
<br>
<br>
<hr>

## Validation Cancellation Payload
The below details the specific guidance around the use of key resources required to create a cancellation of a validation request. See [ServiceRequest - Request - Cancelled](https://simplifier.net/nhsbookingandreferrals/messagedefinition-barsmessagedefinitionservicerequestrequestcancelled) message definition for details.

@@@@@@ Needs writing  or linking to the CANCEL section @@@@@???????
<br>

<hr>
<div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i>
    <b> Important:</b> 
    The sections below show elements in key resources that extend UK Core. Where no table is present, the basic UK Core resource is used unaltered.
</div>