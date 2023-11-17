---
topic: core-SPMessageHeader
---

# {{page-title}}

## MessageHeader Resource
All BaRS payloads (FHIR message bundles) require a **MessageHeader** FHIR resource to provides key information to drive workflow and start interpreting the data contained within. This resource is a central to making a request or aysnchrounous response. 

The **MessageHeader** resource contains the following element which **must** be used as outlined: 
* **MessageHeader.source** -  stipuates where the payload orginated. The Sender **must**, under **MessageHeader.source.endpoint**, include a valid URI which could be used as a NHSD-Target-Identifier (their reference on the Endpoint Catalogue) for the Receiver to send an asynchronous response.
* **MessageHeader.destination** - who the payload is intended for, including reference to an Organisation resource and a valid URI which is the NHSD-Target-Identifier (their reference on the Endpoint Catalogue) the payload is being sent to.
* **MessageHeader.eventCoding** - determines the 'type' of payload, whether booking, referral, request or asynchrnous response. The value **must** be populated from this [CodeSystem](https://simplifier.net/NHSBookingandReferrals/message-events-bars). In referrals, this value combined with the *ServiceRequest.category* element, allows supports for different styles of referral to support various use-cases. The value **must** be populated from this [CodeSystem](https://simplifier.net/NHSDigital/message-category-servicerequest).
* **MessageHeader.reason.code** - indicates whether the message is '**new**' or an '**update**' to something the Receiver is already aware of. The value **must** be populated from this [CodeSystem](https://simplifier.net/NHSBookingandReferrals/message-reason-bars)
* **MessageHeader.focus** -  specifies the root resource through which to start interpreting the payload
* **MessageHeader.definition** - specifies the [MessageDefinition](https://simplifier.net/nhsbookingandreferrals/~resources?category=Example&exampletype=MessageDefinition&sortBy=DisplayName) the payload **must** adhere to and **must** be rejected if it fails to do so. Note: payload conformance to MessageDefinitions is not checked as part of FHIR validation

When a Receiver begins to process the payload, they **must** initially ensure it is for them and they know who it is from:
* check the **MessageHeader.destination** and verify the **MessageHeader.destination.receiver.reference** refers to their Organisation. 
* check the **MessageHeader.destination.endpoint** is, the Service ID they are expected to be processing the request on behalf of. 
* Store NHSD-Target-Identifier under **MessageHeader.source.endpoint** from the Sender to enable an asynchronous response back. Not all workflows will require this type of response but this data must be stored for audit purposes.

The other elements in MessageHeader drive workflow, check **MessageHeader.eventCoding** to know whether a booking or referral payload is being sent and whether this is an initial or update request or an asynchronous response to a pre-existing request. There are various styles of referral too, a request could be made for a straight 'transfer of care' or, currently, something termed a 'validation' where one service requested another to check the outcome they have reached. The intention being as more use-cases come onboard, this list will expand further and provides BaRS the malleability to support further complexity of referrals. Combining the **MessageHeader.eventCoding** with the **ServiceRequest.cateory** provides this functionality. <mention use case categories??> 

Once the above checks have been made, the detail of the payload can start to be unpacked and processed. The structure of the payload **must** be checked first to ensure it adheres to the **MessageHeader.definition** it claims to. The  [MessageDefinitions](https://simplifier.net/nhsbookingandreferrals/~resources?category=Example&exampletype=MessageDefinition&sortBy=DisplayName) will principally be defined by BaRS, at a national level (although bespoke defintions can be used through BaRS), and the Receiver is checking to ensure all mandatory FHIR resources are present and they meet the intended cardinality. This is a manual, business logic, check and not something which is supported through standard FHIR validation of the payload (bundle). 
**MessageHeader.focus** is the root resource through which the payload is intended to be understood. In an initial referral request, this will typically be the **ServiceRequest** FHIR resource. This root will link to other resources to build a narrative for the payload, for example, the **ServiceRequest** will link to the **Encounter** which led to the referral being made and the **Careplan** detail how next actions. The Entity Relationship Diagrams (included in each {{pagelink:Home/Applications/BaRS-Applications/Applications, text:Application}}) are used as a visiual representation of the FHIR resource links in the payloads.

<br>
<br>


### Asynchronous Response Workflows

For certain {{pagelink:Home/Applications/BaRS-Applications/Applications, text:Applications}}, an initial request by a Sender expects an asynchrnous response (as opposed to an HTTP synchronous response (200) message). These responses are defined by the workflow of the Application and may be consistently returned or conditional. When an asynchronous response is initiated, the original Sender and Receiver roles are switched, the Sender becoming the Receiver and visa versa. This allows BaRS to support complex workflows through support for mulitple requests (initial and update) and, potentially, multiple asynchronous responses, for example, an initial status update followed by a more detailed final outcome (as defined in {{pagelink:Home/Applications/BaRS-Applications/Applications/BaRS-APP4, text:Application 4}}). 
The asynchronous response should be thought of as merely another payload, adhering to all the same rules as an initial request or update. Similarly, Sender and Receiver roles are intended to be interchangeable in BaRS and, in most BaRS Applications a supplier is expected to build both Sender and Receiver functionality, something which is reflected in the {{pagelink:pagelink:Home/Assure/Assure, text:assurance process}}, especially {{pagelink:Home/Core, text:BaRS Core}}.

Where the workflow dictates an asynchronous response is to be sent, the Sender (originally the Receiver) **must** populate: 
* **MessageHeader.response.identifier** with the **Bundle.Id** of the original request payload and set the **MessageHeader.response.code** value to 'ok'.
* Additionally, they **must** follow the above guidance on populating the **MessageHeader**. 








