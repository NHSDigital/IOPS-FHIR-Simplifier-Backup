---
topic: core-SPMessageHeader
---

# {{page-title}}

## MessageHeader Resource
All BaRS message bundles require a **MessageHeader** to identify key pieces of information for each request or response. The **MessageHeader** resource is required as part of the technical capability of making a request or response. 

This resource holds key information about the request: 
* **MessageHeader.source** -  where the request has come from
* **MessageHeader.destination** - who it is intended for
* **MessageHeader.eventCoding** - what type of request it is 
* **MessageHeader.focus** -  and how to start interpreting the request. Note focus will change in a response

The Requester **must**: 
* include a NHSD-Target-Identifier (their reference on the Endpoint Catalogue) under **MessageHeader.source.endpoint**, to which the Responder is able to direct a response back to, regardless of whether they expect a response or not. 

The Responder to the request **must**:
* check the **MessageHeader.destination** and verify the **MessageHeader.destination.receiver.reference** refers to their Organisation. 
* check the **MessageHeader.destination.endpoint** is, the Healthcare Service ID they are expected to be processing the request on behalf of. 
* Store NHSD-Target-Identifier under **MessageHeader.source.endpoint** from the Requester to enable a response back if required.

The type of request **must** be checked next and there are three important elements which drive workflow: 
* **eventCoding** - determines the type of request. The value **must** be populated from this [CodeSystem](https://simplifier.net/NHSBookingandReferrals/message-events-bars) and will always be referral for this Application.
* **reasonCode** - indicates whether the message is '**new**' or an '**update**' to something the Responder already has. The value **must** be populated from this [CodeSystem](https://simplifier.net/NHSBookingandReferrals/message-reason-bars).
* **definition** - specifies the [MessageDefinition](https://simplifier.net/nhsbookingandreferrals/~resources?category=Example&exampletype=MessageDefinition&sortBy=DisplayName) the request **must** adhere to and **must** be rejected if it fails to do so.

Once the above checks have been made, the detail of the request can start to be unpacked and processed:
* The **MessageHeader.focus** provides the key to doing this. It indicates the lens through which the request 'message bundle' **must** be interpreted. 
* In a request in most Applications this element will always point to the **ServiceRequest**. Most other FHIR resources in the 'message bundle' will link to or from the 'focus' resource. 
<br>
<br>


### Response Workflow

Where the workflow dictates an asynchronous response is to be sent, the Responder **must** populate: 
* **MessageHeader.response.identifier** with the **Bundle.Id** of the original request 'message bundle' and set the **MessageHeader.response.code** value to 'ok'.
This resource holds key information about the request: 
* **MessageHeader.source** -  where the request has come from
* **MessageHeader.destination** - who it is intended for, the original Requester. 
* **MessageHeader.focus** -  the focus in a response will be the new Encounter. 

When generating asynchronous Response messages (as opposed to an HTTP synchronous response (200) message), where a Responder is sending a 'message bundle' back; 
The Responder **must**: 
* take and store this value, along with the **Bundle.Id** value, to send a response message back to the Requester through the BaRS API Proxy. 







