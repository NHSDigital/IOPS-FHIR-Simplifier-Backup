---
topic: Profile-England-Task
---
# StructureDefinition-England-Task


<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'EnglandTask'
select
	Canonical_URL: url,
  Current_Version: version,
  Last_Updated: date,
	Description: description
```
</div>
<br>

@```
from
	StructureDefinition
where
	name = 'EnglandTask'
select
	Profile_Purpose: purpose
```

<nocheck>
<div class="tab fhirTree">
 <button class="tablinks active" onclick="openTab(event, 'Snapshot View')">Snapshot View</button>
  <button class="tablinks" onclick="openTab(event, 'Differential View')">Differential View</button>
  <button class="tablinks" onclick="openTab(event, 'Hybrid View')">Hybrid View</button>
   <button class="tablinks" onclick="openTab(event, 'Table View')">Table View</button>
   <button class="tablinks" onclick="openTab(event, 'XML View')">XML View</button>
  <button class="tablinks" onclick="openTab(event, 'JSON View')">JSON View</button>
  <button class="tablinks" onclick="openTab(event, 'Examples')">Examples</button>
</div>

<div id="Snapshot View" class="tabcontent" style="display:block">
  <h3>Snapshot View</h3>
{{tree:https://fhir.nhs.uk/StructureDefinition/England-Task, snapshot}}
</div>

<div id="Differential View" class="tabcontent">
  <h3>Differential View</h3>
{{tree:https://fhir.nhs.uk/StructureDefinition/England-Task, diff}}
</div>

<div id="Hybrid View" class="tabcontent">
  <h3>Hybrid View</h3>
{{tree:https://fhir.nhs.uk/StructureDefinition/England-Task, hybrid}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.nhs.uk/StructureDefinition/England-Task, snapshot}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:https://fhir.nhs.uk/StructureDefinition/England-Task, snapshot}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:https://fhir.nhs.uk/StructureDefinition/England-Task, snapshot}}
</div>

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>Active ERS Advice And Guidance</b> - An example to illustrate a task regarding advice and guidance<br>
{{pagelink:Example-England-Task-ActiveERSAdviceAndGuidance}}
<br><br>
  <b>Check Prescription</b> - An example to illustrate a workflow process for a prescription order to be clinically checked<br>
{{pagelink:Example-England-Task-CheckPrescription}}
<br><br>
<b>Lab Report</b> - An example to illustrate a laboratory report (FHIR DiagnosticReport) needs acknowledging and reviewing<br>
{{pagelink:Example-England-Task-LabReport}}
<br><br>
<b>Validate Referral</b> - An example to illustrate to validate a referral (FHIR ServiceRequest) needs checking before it is sent to a service provider<br>
{{pagelink:Example-England-Task-ValidateReferral}}
<br><br>
<b>Fulfill Patient Referral</b> - An example to illustrate the fulfillment of a Patient referral<br>
{{pagelink:Example-England-Task-FulfillPatientReferral}}
<br><br>
<b>Form Complete</b> - An example to illustrate a task regarding form complete<br>
{{pagelink:Example-England-Task-FormComplete}}
</div>
</nocheck>

---

## Profile Specific Implementation Guidance: ##

#### Definition

 FHIR Task usage and scope:

A Task resource often exists in parallel with clinical resources.

For example, a Task could request fulfillment of a ServiceRequest ordering a Procedure that would result in a Procedure, Observation, DiagnosticReport, ImagingStudy or similar resource. Another example would be a Task that requests fulfillment of a CommunicationRequest to be performed between various actors.

 #### Comment

 Task has three main uses: 

- basic delivery of an order resource (e.g. MedicationRequest or ServiceRequest)
- minor workflow requests (e.g. phone patient, complete form or validate a referral)
- workflow support (centred around complex workflow support and may involves a workflow engine)

---

##### Order Fulfilment

Centres on the fulfilment of the order. It does not contain the order details which are held in a referenced request resource. 
In the diagram below the recipient or fulfiller of the order uses FHIR Task to accept or reject the order, it also uses Task to send `event` updates. 
Note the fulfiller will use other resources to record the details of the fulfilment such as MedicationDispense for a MedicationRequest.

{{render:diagrams-Task-Deliver}}

<b>Examples:</b>

| Task.code | Task.status | Task.focus | Task.requester | Meaning | 
|--|--|--|--|
| fulfill | rejected | MedicationRequest | dispenser | The dispenser is rejecting the fulfilment/deliver of a referenced MedicationRequest. The MedicationRequest is not cancelled |
| fullfill | cancelled | MedicationRequest | any | The requested fulfilment of the MedicationRequest is cancelled. The referenced MedicationRequest is not cancelled |
| fullfill | accepted | MedicationRequest | dispenser | The dispenser is taking responsibility of fulfilling the referenced MedicationRequest. |
| fullfill | completed | MedicationRequest | dispenser | The requested fulfilment of the MedicationRequest is completed. The referenced MedicationRequest can now be changed to completed. |

See the section on `status` for more details.

---

##### Minor Workflow Requests

This is used to implement additional around an order or to record specific workflow requests. These may not have a focused resource reference. It is anticipated they are coded using SNOMED CT.

{{render:diagrams-Task-Action}}

<b>Examples:</b>

| Task.code | Task.focus | Task.requester | Task.owner | Task.reasonCode | Meaning |
|--|--|--|--|--|
| 413292001 Assessment for referral | ServiceRequest | referrer |  clinician | 3457005 Patient Referral | Check the referenced referral is valid. |  
| 182836005 Review of medication |  | clinician | GP | 151715009 Emergency admission, asthma  | Request to review medication following an emergency admission. |  
| 103742009 Renewal of prescription | MedicationRequest | patient | GP |   | Request for a reissue/refill of a medication |  
| 324861000000109 Review of patient laboratory test report | DiagnosticReport | consultant | |   | Request for a lab report to be reviewed. See also <a href="https://nhsconnect.github.io/CareConnectAPI/engage_poc_uhscc.html">UHS Lab Reports</a> | 

The Task.status can be used to indicate fulfilment/delivery status.

---

##### Workflow Support

More advanced workflow is supported, this adds in the use of Task.input and Task.output. This allows the passage of inputs and outputs which may be found in automated workflow activities.

The diagram below is from an acute trusts handling of a received eRS referral request. Each process communicates via the FHIR Task, the first process takes the eRS referral and gets the referral letter from eRS, these are then passed to the clinician for triage. Once triaged, the clinician creates a book appointment Task which the admin's action.

{{render:diagrams-Task-automated}}

---