---
topic: APP6-Responses
---

## {{page-title}}

<br>

## Referral Response Payload (Status update)
This section provides guidance on the use of key resources, for the Receiver to create a Referral Response (Status update) to return to the Sender. See [ServiceRequest - Response](https://simplifier.net/nhsbookingandreferrals/bars-messagedefinition-servicerequest-response-referral-short) message definition for details of resources required for this payload.

*Note that Receivers will also have to build the capability to receive and process the Referral Request and Cancellation payloads*

For Referral Response example bundles see:
* [Referral Response - CAD to CAD Out of area](https://simplifier.net/nhsbookingandreferrals/dcd2aaa9-efe2-4df2-bb34-ad4ee9a41f28)
* [Referral Response - CAD to CAD Mutual Aid request rejection](https://simplifier.net/nhsbookingandreferrals/ca337cfa-f564-4948-97bf-4134968caba6)
* For additional example bundles please check [BaRS Example Bundles](https://teams.microsoft.com/l/message/19:775ed072-6a81-45d5-9e19-c38e108efe79_d86b2d01-da33-4982-8276-19d86a303b16@unq.gbl.spaces/1724861855443?context=%7B%22contextType%22%3A%22chat%22%7D)
<br>

### MessageHeader Resource
For detailed information on the use of MessageHeader please refer to the {{pagelink:core-SPMessageHeader-1.1.4, text:Standard Pattern - Message Header}}. 

The MessageHeader resource in the Referral Response should have the following resource elements set as follows:
* **MessageHeader.eventCoding** - **must** be populated with 'servicerequest-response'
* **MessageHeader.reasonCode** - **must** be 'new'
* **MessageHeader.focus** - **must** reference the Responder's current Encounter FHIR resource
* **MessageHeader.definition** - **must** adhere to [Referral Response](https://simplifier.net/NHSBookingandReferrals/BARS-MessageDefinition-ServiceRequest-Response-Referral-Short/~json) Message definition.
* **MessgeHeader.Response** - **must** be the original request BundleID

### ServiceRequest Resource
The *ServiceRequest* reflects that sent by the Requester, and maintains the active state of the referral. The *ServiceRequest.status* at this point would stay as 'active'.

There are two *coding* entries within *ServiceRequest.category* which are key to driving workflow:

1. Denotes the type of referral e.g. Transfer of care 
2. Denotes the use case and must be populated with the relevant use case from [use-case CodeSystem](
https://simplifier.net/nhsbookingandreferrals/usecases-categories-bars)  e.g. Out of area, Mutual Aid or Call Assist. Please refer to the guidance in {{pagelink:core-SPUseCaseCategories-1.1.4, text:use-case categories}}

### Encounter Resource
The Responder's current *Encounter* is the focus resource in the Referral Response. This was originally the 'planned' Encounter created by the Receiver in the synchronous response to the Referral Request. 

This *Encounter* is used to represent the interaction between the patient and the Receiver healthcare service provider. 

When sending an Referral Response the Receiver **must**:
* Include the Receiver's current *Encounter* as the focus resource of the Referral Response
* Include the current *Encounter.status* on the Receiver's current *Encounter*. This is to indicate to the Sender the progress of the case. 

## Referral Response Payload (Reject referral) 
This section provides guidance on the use of key resources, for the Receiver to create an Referral Response (Status update) to return to the Sender in order to reject a **Mutual Aid Request or Call Assist Request**. See [ServiceRequest - Response](https://simplifier.net/nhsbookingandreferrals/bars-messagedefinition-servicerequest-response-referral-short) message definition for details of resources required for this payload.

This follows the payload for the Referral Response (Status Update) with minor changes to the guidance for the Encounter Resource:
### Encounter Resource

When sending an Referral Response the Receiver **must**:
* Include the Receiver's current *Encounter* as the focus resource of the Referral Response
* Include the current *Encounter.status* on the Receiver's current *Encounter*. This is to indicate to the Sender where a Call Assist or Mutual Aid request has been rejected.
* *Encounter.reasonCode* to be included on the Receiver's current *Encounter* to provide the reason for rejection.

<br>

<hr>
<div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i>
    <b> Important:</b> 
    The sections below show elements in key resources that extend UK Core. Where no table is present, the basic UK Core resource is used unaltered.
</div>