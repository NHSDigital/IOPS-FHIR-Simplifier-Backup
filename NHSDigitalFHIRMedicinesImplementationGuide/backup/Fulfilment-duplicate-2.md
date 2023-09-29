## {{page-title}}

Prescription fulfilment is modelled using the FHIR {{pagelink:NHSDigital-Task}} resource. This `Task` has links to both the MedicationRequest and MedicationDispense resources from `prescription-order` and `dispense-notification` messages. Prescription Managment acts on the Task resource only.

{{render:erd-eps}}

A summary of FHIR Task is below:

| FHIR Task | Description | 
|--
| status | The current status of the `prescription-order` or `dispense-notification`, e.g. accepted, completed, in-progress, etc |
| code | The type of Task, either `prescription-order` or `dispense-notification` |
| for | The NHS Number of the Patient the Task is for |
| requester | Who is created the Request (`prescription-order`) or the Event (`dispense-notification`) |
| owner | Who is responsible for actioning the request (normally the pharmacy for `prescription-order`) |
| input | Pointers to the MedicationRequest which are accessed by  {{pagelink:EPSQueryAPI}}
| output | Pointers to the MedicationDispense which are accessed by  {{pagelink:EPSQueryAPI}}

This Task resource is becomes available on receipt of a {{pagelink:PrescriptionOrder}} and is then updated by the other workflow messages. the Task will be given a status of 'requested', this is item 1 in the diagram below:

{{render:WorkflowOverview}}

When the prescription is released by a pharmacy (item 2) the status changes to 'accepted'.
When EPS receives a Prescription Dispense (item 3) the status will change to 'in-progress'. If all items in the Presciption Dispense state they are completed, the Task status will change to 'completed'.

The current status of the prescription can be viewed via the {{pagelink:PrescriptionTrackerAPI}}


<br>

In a similar manner `dispense-notification` workflow events and the EPS generated `prescription-order` for continuous-repeat-dispensing, are also represented as sub Tasks.

{{render:erd-task}}



The Task (code = prescription-order) interactions are:

- prescription release {{pagelink:DownloadPrescriptionfromEPS.md}}
- dispense proposal return {{pagelink:ReturningPrescriptionstoEPS.md}}

The Task (code = dispense-notification) interactions are:

- dispense withdraw {{pagelink:Canceladispensenotification.md}}

<br> 
