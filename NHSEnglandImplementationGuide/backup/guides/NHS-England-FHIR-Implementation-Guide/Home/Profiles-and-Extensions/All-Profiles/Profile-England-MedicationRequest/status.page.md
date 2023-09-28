## `status`

<b>Definition</b><br>

A code specifying the current state of the order. Generally, this will be active or completed state.


| Code| Definition | 
|--
|active|The prescription is 'actionable', but not all actions that are implied by it have occurred yet. It has not been dispensed or filled. |
|cancelled| The prescription is to be cancelled or it has been cancelled been withdrawn before any administrations have occurred. Prescriptions in the process of being cancelled will be regarded as active until all actions are complete. |
|stopped|Actions implied by the prescription are to be permanently halted, before all of the administrations occurred. This should not be used if the original order was entered in error.| 
|completed|All actions that are implied by the prescription have occurred.| 

### Logical medicationRequest status transitions
  This state transition diagram is an enhancement over the generic State Machine defined within the FHIR specification. It includes the status values associated with a medication request with transitions applicable to a NHSE implementation.

{{render:Diagrams-medication-request-status-flow}}

---