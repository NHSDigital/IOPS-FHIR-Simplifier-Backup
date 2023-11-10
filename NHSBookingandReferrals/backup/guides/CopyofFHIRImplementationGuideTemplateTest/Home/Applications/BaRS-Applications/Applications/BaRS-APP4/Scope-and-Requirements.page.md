---
topic: APP4-ScopeAndRequirements
---
# {{page-title}}

## Scope Overview

This BaRS Application (application 4) covers only use cases:
* 999 Ambulance Service Trust (AST) validation request to Clinical Assessment Service (CAS)


The payloads and workflow have been designed to support these services. Other {{pagelink:applications, text:BaRS Applications}} offer scope for alternative use cases.

<br>
For this application we will be referring to the actors as 'Requester' and the 'Responder'. A Requester would be the end that created a validation request to be undertaken and completed by the Responder. A Responder would be the end completing the validation request and responding back with the outcome of the assessment to the Requester. Below you can see a table describing this.
<br>
<br>
<img src="https://raw.githubusercontent.com/NHSDigital/booking-and-referral-media/master/src/images/General/ValidationActors.svg" width="500"></img></a>
<br>
<br>

## Functional Scope

**Service Discovery**

* Establishing a service to direct requests to is a mandatory step in the workflow
* There is no restriction on the service discovery tools used. Any are capable of being supported whether national or proprietary
* The service **must** be configured within the BaRS infrastructure (Endpoint Catalogue) before requests can be made to the service

**Validation Request**
* A validation request is a request for the clinical validation of a triage outcome from one service to another 
* The validation request can be sent without having to establish the capacity the service offers
* The validation request  will contain primarily clinical information, indicating the need of the individual and **should** state the anticipated action required by the Receiving service
* Supporting information, other than the assessment, is expected to be included in a validation request, if collected, including:
    * new or existing safeguarding concerns
    * locally held Special Patient Notes
    * external information sources used during initial assessment prior to referral
    * scene safety information
    * timing information to support the timely delivery of care and reporting

**API-M**
* All requests and response associated with BaRS must occur through the BaRS API Proxy

**Constraints**
* Supporting use of Emergency Call Prioritisation Advisory Group (ECPAG) approved Clinical Decision Support Systems only (NHS Pathways, NHS Pathways Clinical Content Support (PaCCS) and Advanced Medical Priority Dispatch System (AMPDS)).
* No guidance provided on display of referral information beyond the {{pagelink:principles_prerequesites, text:Principles for rendering BaRS Payload}}.
* Consent within BaRS will be for Direct-Care only 
* Certificates for Receiving messages to use nhs.uk domains only.
* Receiving endpoints are to be internet facing.
* Clinical Constraints exist - See Hazard Log

## Requirements

**Service Discovery** 
* The service **must** support a unique identifier which the Sender extracts to engage in referral workflows

**Validation Request**
* The Responder **must** accept the Validation Request regardless of whether the patient is known to the service provider
* The Responder **must** accept potential patients who do **<ins>not</ins>** have a national validated identifier e.g. NHS Number
* The Requester **must** send incident location information as part of their request
* The Requester **must** send scene safety information as part of their request
* Any new or existing safeguarding concern, recorded as part of the assessment, **must** be included in the Validation Request
* The Responder **must** clearly identify any included safeguarding concern to the end user
* The Responder **must** accurately represent information made by the Sender to the end user
* The Requester **must** make available the human readable identifier for the referral, included in the HTTP synchronous response, to the end user
* Where the Validation Request was <ins>not</ins> successful, the Responder **must** send an appropriate response. See {{pagelink:failure_scenarios, text:failure scenarios}} for more detail
* Where the Validation Request was <ins>not</ins> successful, the Requester **must** present an appropriate message to the end user. See {{pagelink:failure_scenarios, text:failure scenarios}} for more detail

**Update Validation Request**
*	The Requester **must** be capable of updating any Validation Request made by them, within the current consultation or after the consultation event
*	The Requester **must** retrieve the Validation Request to be updated from the Responder prior to cancellation to ensure they are working with the most up-to date version and it has not already been completed
*	The Requester **must** provide visible confirmation to the end user of the status returned by the Responder, i.e. whether the original Validation Request was successfully updated or not
*	If the update fails, the Responder **must** respond with the most appropriately aligned error. See {{pagelink:failure_scenarios, text:failure scenarios}} for more detail
*	The Responder **must** store all previous versions of the referral
*	The Requester **must <ins>not</ins>** be required to inform the patient of the updating of the referral.  Business/clinical responsibility for informing the patient must remain with the Requester
*  The Requester  **should not** send updates after receiving an Interim Response


**Cancel Validation Request** 
*	The Requester **must** be capable of cancelling any Validation Request made by them, within the current consultation or after the consultation event
*	The Requester  **must** retrieve the Validation Request to be cancelled from the Responder prior to cancellation, to ensure they are working with the most up-to date version and it has not already been completed
*	The Requester  **must** provide visible confirmation to the end user of the status returned by the Responder, i.e. whether the original Validation Request was successfully cancelled or not
*	If the update fails the Responder **must** respond with the most appropriately aligned error 
*	The Responder **must** store all previous versions of the referral
*	The Responder **must <ins>not</ins>** be required to inform the patient of the cancellation of the Validation Request.  Business/clinical responsibility for informing the patient must remain with the Requester

**Interim Validation Response**
*  The Responder **must** send an Interim Validation Response when the clinician starts the consultation in the CAS system. This **must not** be triggered by a clinician attempting to contact the patient or by a welfare call.
*  The Requester **must** process the Interim Validation Response, update the case in the CAD and display the status change to the end user.

**Final Validation Response**
*  The Responder **must** send an Final Response when the clinician has completed the consultation in the CAS system.
*  The Requester **must** process the final response, update the case in the CAD and display the status change to the end user.
* The status on the Final Validation Response **must** indicate to the end user if a ambulance is required and the case has moved to dispatch, or whether the case can be closed or has been closed automatically with no further action required.
* The final triage should form part of the consultation history of the case in the CAD. 
* All triage instances should form part of the audit in the CAD.

**Incident Location**
*  The Requester  **must** include the incident location in the referral request
*  The Responder  **must** include the incident location in the referral response
*  All Locations **must** include a co-ordinate (Eastings/Northings, Lat/Long or What3Words equivalent) or a property location identifier (UPRN, Address and Postcode)

**Timings**
*  The Requester **must** send the Clock start date/Time (T5). Definition as per AmbSys specification
*  The Responder **must** send the validation breach time
*  The Requester **must** send the dispatch (or disposition) code identification datetime in the **final response**:
    - If the Validation ARP code is the same or downgraded from the original 999 triage, this **must** be populated with the original 999 Clock start date/Time (T5).
    - If the Validation ARP code is upgraded from the original 999 triage this **must** be populated with the Dispatch/Disposition code identification date/time determined by the CAS


**Scene Safety**
*  The Requester **must** send scene safety information in the referral
*  Where scene safety questions have not been asked, the Flag resource relating to scene safety  **must** be populated with 'UNK' unknown.
*  The Responder **should** populate the scene safety flag in their system and **must** display scene safety information to end users.
*  The Responder **must** send scene safety information in the final response, including any updates.
*  The Requester **should** update their system scene safety flag with any updates in the response and **must** display scene safety updates to end users

**Contacts** 
* A minimum of one contact (patient or third party) with a contact method (phone, email, etc.) of phone **must** be provided in requests
* All contacts **must** have a rank
* There **must** be only one contact with a rank of 1
* All contacts **must** have at least one contact method (phone, email, etc.)
* All contact methods **must** have a rank
* There **must** be only one contact method with a rank of 1
* The contact ranked 1 and the contact method ranked 1 **must** be the primary callback for the request
<br>
<br>
### Audit
* Sufficient information around any activity through the API and subsequent BaRS workflow **must** be persisted to aid support incidents and audit requirements
<br>
<br>
### Error Handling 
* Suppliers **must** adhere to the {{pagelink:core-ErrorHandling, text:error handling guidance}} 
<br>
<br>
### Non Functional 
* Suppliers **must** adhere to the {{pagelink:core-NFR, text:non functional requirements}}
<br>
<br>
<hr>