### Prescription Orders Overview


### 1. Create the prescription-order message

Detailed instructions can be found {{pagelink:DevelopingPrescriptionOrderMessage-duplicate-2}}

### 2. Add the Digital Signature

The order message {{pagelink:prescription-order-duplicate-2}} is sent to the EPS  `$prepare` endpoint to generate the digitial signature.

Example message {{pagelink:PrescriptionOrderHomecarePrepare-duplicate-2}}

This is added to the `prescription-order` message in a FHIR **NHSDigital-Provenance** resource and the amended `prescription-order` is then sent to the `$process-message` endpoint.

### 3. Send the prescription-order message 

The `$process-message` endpoint follows [FHIR Messaging](https://www.hl7.org/fhir/messaging.html) standards and the operation definition for this can be found here {{pagelink:process-message-duplicate-3}}. The response to this call will be a FHIR Bundle containing **NHSDigital-OperationOutcome** which indicate success or failure, this is also known as `application-acknowledgement` in existing EPS documentation.

Example message {{pagelink:PrescriptionOrderHomecareusingMedicationresource-duplicate-2}}

{{render:process-message-duplicate-2}} 

### 4. Cancel the prescription-order (if required)

Changes such as a cancelling a prescription item (MedicationRequest) are sent within a {{pagelink:prescription-order-update-duplicate-2}} message to the same `$process-message` endpoint the intial order was sent to and will respond with an `application-acknowledement`. This does not indicate the prescription items have been cancelled just the request has been accepted. 
Conformation the prescription has been updated is returned via a {{pagelink:prescription-order-response-duplicate-2}} message. 

Example update message {{pagelink:PrescriptionOrderHomecareUpdate-duplicate-2}}

### 4a. Cancellation Response Messages

Example update response message  {{pagelink:PrescriptionOrderHomecareResponse-duplicate-2}}

{{render:process-update-message}}

Multiple responses to the {{pagelink:prescription-order-update-duplicate-2}} may be received. 

{{render:process-update-message-multi}}

At present the delivery method for responses responses has not been defined.
