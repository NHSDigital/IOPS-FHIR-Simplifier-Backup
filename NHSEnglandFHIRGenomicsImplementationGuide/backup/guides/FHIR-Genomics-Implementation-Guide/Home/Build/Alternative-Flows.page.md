## {{page-title}}

The full end-to-end process, including alternative flows, have been documented in the National Genomic Testing Process, available on the [NHS Futures site](https://future.nhs.uk/connect.ti/NHSgenomics/view?objectId=157008581).

The dotted lines in the NGTP diagram indicate messages between organisations (within scope for the Genomics FHIR specification). These messages have been detailed below, alongside the resource types needed to represent the request:

**1.01** Create Test Request (As NGTD)
* Initial test order message bundle, including ServiceRequest

**2.24** Notify ordering entity of processing failure (invalid test/sample or request not present/unsatisfied condition or test dependent time frame/unsuccessful sample processing/unsuccessful interpretation)
* Task with focus of ServiceRequest marked with status 'on-hold' or 'failed' with statusReason indicating the reason

**RS1** Request for Specialist Test (from remote GLH)
* Same as 1, ServiceRequest may be marked as a reflex test if requested in response to another test

**2.04** Request Sample (from external lab)
* Task with owner = external lab, input = patient identifier, output = Specimen required (This may be handled offline to limit scope for the FoT phase of the central service)

**6.03** Send Sample Availability Confirmation
* Specimen marked as available

**2.07** Forward Order Request (send away sample)
* Update Sample Management Task with new send-away lab as owner with input Specimen

**2.08** Forward Order Request (send away DNA/RNA) (TODO: draft example of request)
* Update Processing Task with new send-away lab as owner with input sub-Specimen (DNA sample)

**RS2** Request for Specialist Interpretation (from remote GLH)
* Receive Processing Task with GLH/lab as owner with note/status describing work required (Interpretation/DiagnosticReport) (TODO: draft example of request)

**2.10, 2.12, 5.03, 5.05** Send-away for data processing or interpretation
* Send Processing Task with remote GLH/lab as owner with note/status describing work required (Data-processing/Interpretation)

**5.08** Mark completion of reflex/confirmatory test
* Task marked as completed, reflex-order ServiceRequest also marked completed

**2.15, 5.33** Request for further clinical detail for Genomic MDT
* Task sent to Additional Contact on ServiceRequest with note indicating the required information

**1.03** Provide MDT with further clinical details
* Collection of clinical resources fulfilling the Task request (e.g. Condition/Observation etc.)

**2.18** Reflex test required
* Additional ServiceRequest test order transaction bundle based on original request, marked as reflex-order 

**2.19, 5.11.1** Distribute report
* DiagnosticReport test result transaction bundle, sent to central service, forwarded to reporting address

## Replacement and updates

Replacement to existing resources, e.g. ServiceRequests, is expected to be performed through POSTing of a replacement ServiceRequest which references the replaced ServiceRequest through the .replaces field. 

Updates to ServiceRequests or DiagnosticReports can be made through PUT or PATCH requests to the central broker, using the same ids and identifiers. It is expected notifications would be sent out to all subscribers to a resource on any change, regardless of the HTTP verb used e.g. POST, PUT, PATCH, DELETE. This will ensure all updates to requests or reports are communicated to interested parties.

## Additional Task interaction scenarios/sequence diagrams

### EHR → GLH (Home) → EHR

{{render:diagrams-interaction1}}

### EHR → GLH (Home) → GEL → GLH (Home) → EHR

{{render:diagrams-interaction2}}

### EHR → GLH (Home) → GLH(Remote) → LGL → GLH (Remote) → GLH (Home) → EHR

{{render:diagrams-interaction3}}

### Multiple labs
This use case can also include tests being sent to multiple labs. Each lab creates an interim report which the GLH would poll for, consumes and creates a final test report by combining the interim test reports.

{{render:diagrams-interaction4}}

### Test Request Cancelled
There are scenarios where test requests can be updated, cancelled or retracted so the API and notification mechanisms can be used to support these scenarios as well.

{{render:diagrams-interaction5}}

### Black Box / Non-Integrated Labs
As the uptake of the test order service is rolled out, there will be a period where not all labs and services will be onboarded. This could be attributed to various factors around regional acceleration, informatics maturity etc. In these scenarios the expectation is that a task will still be created on test order service but managed by the integrated systems/services upstream of the transition to local processes. 

When the test report is received, it may arrive at the GLH, LIMS or somewhere else in the requesting organisation. When the test report arrives and is logged onto the local system this should propagate through to result in a DiagnosticReport being created on the test order service to complete the test request and create a complete record on the test order service for visibility to other organisations.

Where the only non-integrated organisation is a lab, the test order service could be integrated with the National Pathology Exchange (NPEx) to receive the test report, as most labs are integrated with the service. The use of correct identifiers would be needed to correctly exchange information between the test order service and NPEx.

{{render:diagrams-interaction6}}