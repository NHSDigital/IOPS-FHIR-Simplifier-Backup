### Prescription Orders Overview


### 1. Create the prescription-order message

Detailed instructions can be found {{pagelink:DevelopingPrescriptionOrderMessage}}

### 2. Add the Digital Signature

The order message {{pagelink:prescription-order}} is sent to the EPS  `$prepare` endpoint to generate the digitial signature.

Example message {{pagelink:PrescriptionOrderHomecarePrepare.md}}

This is added to the `prescription-order` message in a FHIR {{pagelink:DM-Provenance}} resource and the amended `prescription-order` is then sent to the `$process-message` endpoint.

### 3. Send the prescription-order message 

The `$process-message` endpoint follows [FHIR Messaging](https://www.hl7.org/fhir/messaging.html) standards and the operation definition for this can be found here {{pagelink:process-message}}. The response to this call will be a FHIR Bundle containing [OperationOutcome](https://simplifier.net/guide/NHSDigitalSpine/Spine-OperationOutcome) which indicate success or failure, this is also known as `application-acknowledgement` in existing EPS documentation.

Example message {{pagelink:PrescriptionOrderHomecareusingMedicationresource.md}}

{{render:process-message-duplicate-2}} 

### 4. Cancel the prescription-order (if required)

Changes such as a cancelling a prescription item (MedicationRequest) are sent within a {{pagelink:prescription-order-update}} message to the same `$process-message` endpoint the intial order was sent to and will respond with an `application-acknowledement`. This does not indicate the prescription items have been cancelled just the request has been accepted. 
Conformation the prescription has been updated is returned via a {{pagelink:prescription-order-response}} message. 

Example update message {{pagelink:PrescriptionOrderHomecareUpdate.md}}

### 4a. Cancellation Response Messages

Example update response message  {{pagelink:PrescriptionOrderHomecareResponse.md}}

{{render:process-update-message}}

Multiple responses to the {{pagelink:prescription-order-update}} may be received. 

{{render:process-update-message-multi}}

At present the delivery method for responses responses has not been defined.
