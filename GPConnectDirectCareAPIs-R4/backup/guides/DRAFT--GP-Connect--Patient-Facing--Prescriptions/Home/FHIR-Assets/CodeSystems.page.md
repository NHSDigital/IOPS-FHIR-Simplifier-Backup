## {{page-title}}

There is one set of CodeSystems to be used with this API.

{{render:https://fhir.nhs.uk/England/CodeSystem/England-PFSPrescriptionOrderingParameter}}

#### preferred-performer
The preferred performer code is to be used when the patient wants the prescription to be dispensed by a one-off pharmacy (not their nominated one on the Personal Demographics Service (PDS)).

This code should be added to the Task.Input upon making the request.

#### sent-to-eps
This is to indicate that the prescription request has been sent to EPS in order to be dispensed. This will enable tracking via EPS using the corresponding ID.