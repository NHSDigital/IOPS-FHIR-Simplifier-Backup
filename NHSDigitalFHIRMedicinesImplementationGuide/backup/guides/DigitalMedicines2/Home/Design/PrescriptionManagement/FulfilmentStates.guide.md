## {{page-title}}

EPS has an internal state engine which is used to manage the processing of the prescription (FHIR Task).

{{render:task-state-engine}}

### Direct State Changes

The Task fulfilment state can be manipulated directly via 

- {{pagelink:ReturningPrescriptionstoEPS-duplicate-3}}

The updated Task received by EPS follows these rules:

| Task.status | Task.statusReason | Description | Resulting Task.status |
|-- 
| failed | 0004 | Expired | |
| cancelled | 0005 | Cancelled | |
| rejected | 0007 | Not Dispensed | ready |

<br>

- {{pagelink:PrescriptionRelease-duplicate-2}}

On release the Task in EPS is changed to: 

| Task.status | Task.statusReason |  
|-- 
| accepted | 0002 | With Dispenser | 

<br/>

- {{pagelink:CancelADispenseNotification-duplicate-2}}

Cancelling dispense-notifications can also result in a Task.status change.

| Condition | Task.status | Task.statusReason |  
|-- 
| If no dispensing activity recorded | accepted | 0002 | With Dispenser | 

<br/>

### Indirect State Changes

It indirectly manipulatd by [Prescription Ordering]({{pagelink:index-duplicate-48}})
Requests and [Prescription Dispensing]({{pagelink:index-duplicate-45}}) events.

<br/>



#### MedicationRequest.status (Prescription Order)

| MedicationRequest.status | condition | Task.status | Notes |
|--
| active | if nominated | requested | Task is created in EPS|
| active | if not nominated | ready | Task is created in EPS|
| cancelled | if not with a dispenser | cancelled | | 
| cancelled | if with a dispenser (active or not) | failed | when the dispenser returns the prescription this will turn to cancelled |

<br/>

#### MedicationDispense.status and MedicationDispense.prescriptionStatus

The Task status is linked to the prescription status held in {{link:https://fhir.nhs.uk/StructureDefinition/Extension-EPS-TaskBusinessStatus}}

| MedicationDispense.prescriptionStatus | Description| Task.status | MedicationRequest.status |
|--
| 0003 | With Dispenser - Active | in-progress | |
| 0006 | Dispensed | completed | completed |

<br/>


