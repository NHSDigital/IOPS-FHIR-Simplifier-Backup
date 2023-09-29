## {{page-title}}

Prescription fulfilment is modelled using the FHIR {{pagelink:NHSDigital-Task-duplicate-2}} resource. This `Task` has links to both the MedicationRequest and MedicationDispense resources from `prescription-order` and `dispense-notification` messages. Prescription Managment acts on the Task resource only.

{{render:erd-eps}}

A summary of FHIR Task is below:

| FHIR Task | Description | 
|--
| status | The current status of the `prescription-order` or `dispense-notification`, e.g. accepted, completed, in-progress, etc |
| code | normally `fulfil` |
| reasonCode | The Task reason, either `33633005 - Prescription of drug` or `373784005 - Dispensing medication` |
| for | The NHS Number of the Patient the Task is for |
| requester | Who is created the Request (`prescription-order`) or the Event (`dispense-notification`) |
| owner | Who is responsible for actioning the request (normally the pharmacy for `prescription-order`) |
| input | Pointers to the MedicationRequest which are accessed by [EPSQueryAPI]({{pagelink:index-duplicate-54}})
| output | Pointers to the MedicationDispense which are accessed by  [EPSQueryAPI]({{pagelink:index-duplicate-54}})

This Task resource is becomes available on receipt of a [PrescriptionOrder]({{pagelink:index-duplicate-48}}) and is then updated by the other workflow messages. the Task will be given a status of 'requested', this is item 1 in the diagram below:

{{render:WorkflowOverview}}

When the prescription is released by a pharmacy (item 2) the status changes to 'accepted'.
When EPS receives a Prescription Dispense (item 3) the status will change to 'in-progress'. If all items in the Presciption Dispense state they are completed, the Task status will change to 'completed'.

The current status of the prescription can be viewed via the {{pagelink:PrescriptionTrackerAPI-duplicate-2}}


<br>

In a similar manner `dispense-notification` workflow events and the EPS generated `prescription-order` for continuous-repeat-dispensing, are also represented as sub Tasks.

{{render:erd-task}}



The Task (code = prescription-order) interactions are:

- prescription release {{pagelink:prescriptionrelease-duplicate-2}}
- dispense proposal return {{pagelink:ReturningPrescriptionstoEPS-duplicate-3}}

The Task (code = dispense-notification) interactions are:

- dispense withdraw {{pagelink:Canceladispensenotification-duplicate-2}}

<br> 
