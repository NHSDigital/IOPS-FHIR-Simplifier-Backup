## `focus` 
 
 <b>Definition</b><br>

 **e-RS**

Reference to the resource which is the focus of the action 

**EPS Only**

This will be the `Bundle.identifier` of the message this Task is acting on. 
For Tasks with a reasonCode of `373784005 - Dispensing medication`  this will be a `dispense-notification` message. 
For Tasks with a reasonCode of `33633005 - Prescription of drug` this will be the `prescription-order` message from the Task/$release operation.


 <b>Comment</b><br>

 Tasks are often generated as a consequence of other workflows or relate to FHIR Workflow resources. For example a repeat medication request will be related to a previous `MedicationRequest` or a medication reconciliation may relate to a hospital admissions `Encounter/EpisodeOfCare`. This is carried in the `focus` element.

`focus` can be omitted. For example if an ED generated a Medication Review as a result of COPD Emergency encounter they may chose to include a reference to the Encounter but they may decide instead to use a more specific reasonCode such as `394720003 | Asthma medication review`.

---