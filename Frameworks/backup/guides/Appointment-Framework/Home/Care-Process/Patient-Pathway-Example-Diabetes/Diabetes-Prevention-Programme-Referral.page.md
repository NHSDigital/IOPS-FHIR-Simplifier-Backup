## {{page-title}}

### Current Process

The current process does not define any technical implementation standards. It does state UK SNOMED coding which largely mirrors the [FHIR Workflow Communication State Definitions](https://hl7.org/fhir/R4/workflow-communications.html#12.6.2)

{{render:diagrams-NHS-England-Clinicals-Current-Workflow-Sequence-Diagram-SNOMED}}

The diagram shows a series of interactions between the GP Surgey (placer), Patient and Provider. This communication has not been defined by the programme and is probably done via a combination of verbal/SMS/email/letter methods. The result of this communication is stored as an event in the GP Record (in GP Connect this would be surfaced as a FHIR Observation). It is likely the GP or other system tracks the status of these requests in a workflow or task manager.

So for use case example, at the end of the `NHS Health Check`, Dawn offered the Diabetes Prevention Programme as an intervention. If William declined this offer, an Observation would have been recorded using SNOMED CT `Referral to NHS Diabetes Prevention Programme declined (1025301000000100)` in the GP system.

In our example William accepted the offer and the referral process was started. This involved William completing a `Diabetes Risk Assessment`. How the GP Surgery asks the provider to fulfil the referral is similar, the request is sent and the provider responds with accepted which results in `NHS Diabetes Prevention Programme started (1025271000000103)` being recorded in the EPR. 
When the intervention is compeleted/abandoned the provider will communicate with the surgery (verbal, sms, email, etc) and this results in `NHS Diabetes Prevention Programme completed (1025251000000107)` or  `NHS Diabetes Prevention Programme not completed (1025211000000108)` being recorded in the EPR.

### FHIR Workflow applied to the current process

FHIR Workflow focuses on the communication, it does not focus on the exchanging of health care records. These are handled via the Query API (see {{pagelink:Home/Technical-Framework/Query-API}}).

With FHIR Workflow all the verbal/sms/email/fax communication can be replaced by the FHIR Task resource.

{{render:diagrams-NHS-England-Clinicals-Current-Workflow-Sequence-Diagram-with-FHIR}}

For example, a request to Leeds Community Healthcare NHS Trust (RY6) could look like this:

{{pagelink:Home/Artefacts/Task/Diabetes-Prevention-Programme-Referral---requested.page.md}}

The response from the LCH to the surgery is very similar. In the example below, only the status has changed to `accepted`.

{{pagelink:Home/Artefacts/Task/Diabetes-Prevention-Programme-Referral---accepted.page.md}}

When LCH informs the surgery, the intervention is complete, again this is very similar with the status changed to `completed`.

{{pagelink:Home/Artefacts/Task/Diabetes-Prevention-Programme-Referral---completed.page.md}}

The above is a very basic description of FHIR Workflow. It can be extended, for example let's assume William decided to swap to self-management of his weight via physical activity. In this case the provider sends back a Task with the status of `cancelled` with a note indicating the reason why.

{{pagelink:Home/Artefacts/Task/Diabetes-Prevention-Programme-Referral---cancelled.page.md}}

### FHIR ServiceRequest and supporting information

We have purposely not discussed the referral itself. This can be found on {{pagelink:Home/Artefacts/ServiceRequest/Diabetes-Prevention-Programme-Referral.page.md}}. 
Where a `Query API` is available, in FHIR Workflow **this is not sent to the provider** and instead shared with them. 
This is also true of supporting information which in this case is the {{pagelink:Home/Artefacts/QuestionnaireResponse/Diabetes-Risk-Score-Completed-Form.page.md}}

*It is highly recommended that referrals, supporting information and workflow are NOT combined into one interaction.* This can become very difficult and costly to implement and define.

This is a big change from current ways of working and other methods of sharing this information may need to use while sharing of data becomes prevalent. FHIR Workflow has a list of [communication patterns](https://hl7.org/fhir/R4/workflow-communications.html#commpatternslist) which may assist. 
In NHS England systems the following communication patterns are used:

- Electronic Referral System (eRS) broadly aligns with [Option H: Workflow Broker](https://hl7.org/fhir/R4/workflow-management.html#optionh) where Worklist Items correspond to FHIR Task.
- Bookings and Referrals Standard (BARS) is like [Option D: Messaging request from placer to filler & acknowledgment](https://hl7.org/fhir/R4/workflow-ad-hoc.html#optiond)


### Frameworks Used

| Framework | Description |
|--
| {{pagelink:Home/Technical-Framework/Workflow}} | Workflow is used to communicate between the providers to deliver the referral. | 
| {{pagelink:Home/Technical-Framework/Query-API}} | A shared Query API was used by providers to review the incoming referral request, view existing patient and share progress on the care delivery. | 
| {{pagelink:Home/Technical-Framework/Structured-Data-Capture}} | The output from the Diabetes Risk Evaluation is probably shared as supporting information for the Diabetes Referral, using frameworks this would be shared via `Query API` |
