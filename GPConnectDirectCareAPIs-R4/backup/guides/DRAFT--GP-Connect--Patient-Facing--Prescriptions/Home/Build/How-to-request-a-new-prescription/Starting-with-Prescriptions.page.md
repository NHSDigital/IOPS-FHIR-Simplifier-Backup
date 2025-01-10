## {{page-title}}

If a Patient wishes to start at viewing their Prescriptions, a standard user journey would look like this:

 1. Search by NHS Number to obtain `MedicationRequest` resources related to the patient, using the endpoint: GET /FHIR/R4/Patient/`{NHSNumber}`/MedicationRequest

    This returns a `Bundle` containing `MedictionRequest's` which includes information surrounding the Prescription's to be displayed to the patient. 

    At this stage it is possible to verify which are repeat prescriptions, by the `courseOfTherapyType` and which are still authorized to be reordered. 

 2. Now the id of the validated `MedicationRequest` can be used to create a new request of a prescription reorder.
 
 This will be done the same way, using `Task` and having a `focus` that references the same `MedicationRequest` that has `intent`, the `Task` resource is then used as the requestbody for the endpoint: POST /FHIR/R4/Task/

 3. At this stage the patient can then track the status of the order or send a cancellation (up until the point the request is actioned).
