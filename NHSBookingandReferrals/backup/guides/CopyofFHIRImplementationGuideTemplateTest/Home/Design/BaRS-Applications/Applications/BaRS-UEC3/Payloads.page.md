---
topic: APP3-Payloads
---


## {{page-title}}

## Review everything?????

### MessageHeader Resource
The MessageHeader resource is required as part of the technical capability of making a referral. Rather than providing clinical or administrative content for the end users; the function of all other resources are outlined. This resource holds key information about where the request has come from (*MessageHeader.source*), who it is intended for (*MessageHeader.destination*), what type of request it is (*MessageHeader.eventCoding*) and how to start interpreting the request (*MessageHeader.focus*). 

Any Receiver of the request 'message bundle' **must** first check the *MessageHeader.destination* and verify the *MessageHeader.destination.receiver.reference* refers to their Organisation. The *MessageHeader.destination.endpoint* is, in turn, the Healthcare Service Id they are expected to be processing the request on behalf of. 

The type of request **must** be checked next and there are three important elements which drive workflow: 
* **eventCoding** - determines the type of request, either booking or referral. The value **must** be populated from this [CodeSystem](https://simplifier.net/NHSBookingandReferrals/message-events-bars) and will always be referral for this Application.
* **reasonCode** - indicates whether the message is new or an update to something the Receiver already has. The value **must** be populated from this [CodeSystem](https://simplifier.net/NHSBookingandReferrals/message-reason-bars).
* **definition** - specifies the [MessageDefinition](https://simplifier.net/nhsbookingandreferrals/~resources?category=Example&exampletype=MessageDefinition&sortBy=DisplayName) the request **must** adhere to and **must** be rejected if it fails to do so.

Once the above checks have been made the detail of the request can start to be unpacked and processed. The *MessageHeader.focus* provides the key to doing this. It indicates the lens through which the request 'message bundle' **must** be interpreted. In this Application the element will always point to the ServiceRequest. Most other FHIR resources in the 'message bundle' will link to or from the 'focus' resource. 

When generating asynchronous Response messages (as opposed to an HTTP synchronous response (200) message), where a Receiver is sending a 'message bundle' back to an originating Sender. Firstly, the Sender, in the original request **must** include a NHSD-Target-Identifier (their reference on the Endpoint Catalogue) under *MessageHeader.source.endpoint*, to which the Receiver is able to direct a response back to, regardless of whether they expect a response or not. The Receiver **must** take and store this value, along with the *Bundle.Id* value, to send a response message back to the Sender through the BaRS API Proxy. This is not a workflow in this Application but is used in other BaRS Applications and fundamental to BaRS workflows in general.

If the workflow dictates an asynchonous response is to be sent, the Receiver **must** populate *MessageHeader.response.identifier* with the *Bundle.Id* of the original request 'message bundle' and set the *MessageHeader.response.code* value to 'ok'. 

### ServiceRequest Resource
The 'focus' resource in a referral is the ServiceRequest resource. When the request 'message bundle' is created by the Sender and processed by the Receiver, this is the starting point from which the referral is understood. It provides either the detail or references to all key FHIR resources, for example, the Patient, Encounter and Careplan. The guidance for this resource below provides more granular, element level, detail. A key point when a Sender builds the referral FHIR 'message bundle' is to ensure the *MessageHeader.focus* references the ServiceRequest resource. 

### Encounter Resource
The Encounter is used to represent the interaction between a patient and healthcare service provider. It links with numerous other resources, to reflect the assessment performed. 

In the initial referral request, the Sender will include an Encounter resource as the container for their assessment, which established the need for the referral. This encounter **should** include a reference to the Sender's assessment under *encounter.identifier*. Additionally, the *encounter.episodeOfCare* **must** be populated with a 'journeyId' reference which can be used in subsequent referrals to allow the audit of the route a patient took through service providers to resolve their initial request for care. 

A second Encounter resource is used to transfer the human readable reference of the newly created referral, at the Receiver side. When a referral request is made, the Receiver **should** include a new, secondary, encounter resource with the status of 'planned' in their synchronous HTTP response (200) to the Sender's request. This new 'planned' encounter will have both an Id and an Identifier value, indicating the Receiver's local reference and human readable one, respectively. This secondary, 'planned', encounter is <ins>not</ins> mandatory (cardinality of 0..1), unlike the primary encounter resource (1..1) (See the {{pagelink:Home/Design/BaRS-Applications/Applications/BaRS-APP5/Entity-Relationship-Diagrams.page.md, text:Entity Relationship Diagram}} for reference). The human readable (Identifier) reference is intended to allow Senders to provide something to the patient which they can take between services to support consistent joined up care, although, it is also a useful link for the services themselves to use when discussing a patient's transition of care. The local (Id) reference is not intended to be human readable but rather machine readable.

### CarePlan Resource
The CarePlan resource is used in a referral request to communicate the next steps in care, linking both the 'problem' identified (Condition resource, *careplan.addresses*), following the assessment performed by the Sender, and the required action to move the patient's issue to resolution (Task resource, *careplan.activity.reference*). The Receiver will utilise the detail in this resource to summarise what the previous assessment ascertained about the patient, to be used in any subsequent consultation with the patient. This overall clinical narrative and assessment output is included in this resource, under element *careplan.outcomeCodeableConcept.text*, as 'freetext'.

### Condition Resource 
The Condition resource is used to encapsulate the overall 'problem' the referral intends to resolve for the patient. The detail provided here underpins the rationale for the CarePlan and is a central resource for the Receiver looking for information about the patient and reason for referral.

The key information about the 'problem' is comprised of two components within this Application, *careplan.category* and *careplan.code*. The category is used to qualify the code value, providing additional context to interpret the issue identified. For example, in this Application, the category will stipulate this is a 'presenting complaint', highlighting the provenance of the 'problem' for the Receiver to start their consultation. This is in addition to other specific status fields on the resource. 

### Task Resource
The Task is used to direct the next action(s) required by the Sender making the referral. Task supports in fulfilling Careplan, which also references it. The narrative within the payload starts with the assessment performed by the Sender (*Encounter*), identifying a 'problem' (*Condition*) which a plan of care (*CarePlan*) is established to address. The Sender is unable to support the plan of care so transitions responsibility, via a referral (*ServiceRequest*), while directing the next requested action (*Task*).

This Application utilises two elements within Task to direct the activity and timeframe, using *Task.code* and *Task.restriction*. The code will be a fixed value, indicating that a consultation is being request of the 'Community Pharmacist Consultation Service for minor illness', dictating the action **should** take place within thirty minutes, under the *restriction.period* element.  

### Flag Resource
The Flag resource is used to communicate prospective warnings of potential issues when providing care to the patient. The population of the Flag Resource is optional as not all subjects will have relevant issues.

BaRS Senders **should** populate Flag resources and **should** make adequate provision in their solution to support key flags in BaRS Application workflows, for example, Safeguarding, for this Application. When populating this resource, Senders **must** include both *flag.category* and *flag.code* values using the specific [BaRS CodeSystems](https://simplifier.net/nhsbookingandreferrals/~resources?category=CodeSystem&sortBy=DisplayName).

When a BARS Receiver processes information in a Flag resource;

* they **should** populate a flag in their system, if their solution supports that flag
* they **must** display the information in the Flag resource in a way that supports the associated workflow (i.e. the relevant end users can see it and act upon it)
* rendering of Flag information must be in line with the {{pagelink:Home/About-BaRS/BaRS-Principles-and-Prerequisites/Principles-for-rendering-BaRS-payloads.page.md, text:Principles for rendering BaRS Payload }}.

### Consent 
In the BaRS UEC Applications the level of consent is stipulated to be for 'Direct Care' only. A referral **must** contain a Consent resource and it **must** adhere to the [example](https://simplifier.net/NHSBookingandReferrals/8fc39b95-89a6-45fb-914f-1458a10e9e14/~json) provided under the BaRS FHIR assets. 
<br>

<hr>
<div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i>
    <b> Important:</b> 
    The sections below show elements in key resources that extend UK Core. Where no table is present, the basic UK Core resource is used unaltered.
</div>