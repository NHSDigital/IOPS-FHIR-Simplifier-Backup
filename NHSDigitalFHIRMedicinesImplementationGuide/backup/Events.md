##### {{page-title}}

{{render:erd-eps-event}}

The events API is a potential enhancement to provide notifications of pharmacy events to patients and practitioners. The initial proposal is to follow [FHIR Workflow](https://www.hl7.org/fhir/workflow.html) and use the FHIR {{pagelink:NHSDigital-Task}} resource. 
<br>

The use of {{pagelink:NHSDigital-Task}} will allow refactoring of EPS to send `prescription-order` or `dispense-notification` directly to dispensers and prescribers. 
Both the *Nominated Pharmacy* and *Patient Prescription Token* can be refactored to not use the polling {{pagelink:PrescriptionRelease.md}} operation. 
Instead, they will use the {{pagelink:PrescriptionTrackerAPI}} 
and FHIR Task to either `accept` or `reject` the order (if applicable).

As dispensers can now query EPS via the {{pagelink:PrescriptionTrackerAPI}} by NHS Number, this reduces (removes) the use of prescription tokens.

For dispensers subscribing to the events API, the use of {{pagelink:PrescriptionTrackerAPI}} or 
{{pagelink:PrescriptionRelease.md}} to poll for nominated pharmacy orders will become a backup method.  

{{render:workflow-refactor}}