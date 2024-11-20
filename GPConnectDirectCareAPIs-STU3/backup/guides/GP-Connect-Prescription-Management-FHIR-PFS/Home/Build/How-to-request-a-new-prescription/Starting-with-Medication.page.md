## {{page-title}}

If a patient wants to view their medications, a standard user journey looks like this:

 1. Search by NHS number to obtain `MedicationStatement` resources related to the patient, using the endpoint: GET /FHIR/R4/Patient/`{NHSNumber}`/MedicationStatement.

    This returns a `Bundle` containing `MedicationStatement's` which includes information surrounding the medication to be displayed to the patient. 

    Each MedicationStatement references a `MedicationRequest` with `intent` of `plan`. The `MedicationRequest` is a representation of the prescription, these contain further details about the prescription itself, i.e. whether it's acute or repeat and if it has expired. 

 2. The next stage in the user journey would be to resolve the referenced `MedicationRequest` to obtain the `courseOfTherapyType` of the Prescription (as part of MVP we're only building for reordering of repeat prescriptions, although the API can cater for this), and also to validate that it is a valid authorization that hasn't expired. Use the Endpoint: GET /MedicationRequest/`{id}` for this stage.

    Once the prescription has been validated as authorized and repeat, we can then use the same id to request a reorder of that prescription.

 3. Create a new request of a prescription reorder using `Task` and having a `focus` that has a reference of the same `MedicationRequest` that has `intent`, the `Task` resource is then used as the requestbody for the endpoint: POST /FHIR/R4/Task/

 4. At this stage the patient can then track the status of the order, or send a cancellation up (until the point the request is actioned).

INTERACTION DIAGRAMS TO BE COMPLETED