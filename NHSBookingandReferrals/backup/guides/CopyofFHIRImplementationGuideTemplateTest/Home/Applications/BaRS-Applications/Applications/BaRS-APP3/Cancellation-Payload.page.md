## {{page-title}}

### Overview 
Cancellation is a stripped back request only containing the specific resources a Receiver requires to perform the action. 

### MessageHeader Resource
The MessageHeader resource is required as part of the technical capability of making a referral. Rather than providing clinical or administrative content for the end users; the function of all other resources are outlined. This resource holds key information about where the request has come from (*MessageHeader.source*), who it is intended for (*MessageHeader.destination*), what type of request it is (*MessageHeader.eventCoding*) and how to start interpreting the request (*MessageHeader.focus*). 

Any Receiver of the request 'message bundle' **must** first check the *MessageHeader.destination* and verify the *MessageHeader.destination.receiver.reference* refers to their Organisation. The *MessageHeader.destination.endpoint* is, in turn, the Healthcare Service ID they are expected to be processing the request on behalf of. 

The type of request **must** be checked next and there are three important elements which drive workflow: 
* **eventCoding** - determines the type of request. The value **must** be populated from this [CodeSystem](https://simplifier.net/NHSBookingandReferrals/message-events-bars) and will always be referral for this Application.
* **reasonCode** - indicates whether the message is new or an update to something the Receiver already has. The value **must** be populated from this [CodeSystem](https://simplifier.net/NHSBookingandReferrals/message-reason-bars).
* **definition** - specifies the [MessageDefinition](https://simplifier.net/nhsbookingandreferrals/~resources?category=Example&exampletype=MessageDefinition&sortBy=DisplayName) the request **must** adhere to and **must** be rejected if it fails to do so.

Once the above checks have been made the detail of the request can start to be unpacked and processed. The *MessageHeader.focus* provides the key to doing this. It indicates the lens through which the request 'message bundle' **must** be interpreted. In this Application the element will always point to the ServiceRequest. Most other FHIR resources in the 'message bundle' will link to or from the 'focus' resource. 

When generating asynchronous Response messages (as opposed to an HTTP synchronous response (200) message), where a Receiver is sending a 'message bundle' back to an originating Sender. Firstly, the Sender, in the original request **must** include a NHSD-Target-Identifier (their reference on the Endpoint Catalogue) under *MessageHeader.source.endpoint*, to which the Receiver is able to direct a response back to, regardless of whether they expect a response or not. The Receiver **must** take and store this value, along with the *Bundle.Id* value, to send a response message back to the Sender through the BaRS API Proxy. This is not a workflow in this Application but is used in other BaRS Applications and fundamental to BaRS workflows in general.

If the workflow dictates an asynchonous response is to be sent, the Receiver **must** populate *MessageHeader.response.identifier* with the *Bundle.Id* of the original request 'message bundle' and set the *MessageHeader.response.code* value to 'ok'. 

### ServiceRequest Resource
The 'focus' resource in a referral is the ServiceRequest resource. When the request 'message bundle' is created by the Sender and processed by the Receiver, this is the starting point from which the referral is understood. It provides either the detail or references to all key FHIR resources, for example, the Patient, Encounter and Careplan. The guidance for this resource below provides more granular, element level, detail. A key point when a Sender builds the referral FHIR 'message bundle' is to ensure the *MessageHeader.focus* references the ServiceRequest resource.

Additionally, the *ServiceRequest.occurrencePeriod* **must** be populated with the time that the receiving service must call the patient by (call back time)