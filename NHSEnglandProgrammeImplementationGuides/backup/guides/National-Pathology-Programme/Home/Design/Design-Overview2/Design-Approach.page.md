### Design Approach
The base FHIR R4 specification describes several methods of representing test reports and  [grouping observations](https://hl7.org/fhir/R4/observation.html#obsgrouping). The design approach that has been adopted as part of this implementation guide is summarised below:

* `DiagnosticReport` contains the overall findings and clinical interpretation relating to one or more pathology tests.
* Test results and test groups are defined as `Observations` (using distinct profiles) and are referenced from `DiagnosticReport` using `DiagnosticReport.result`.
* `Observation.hasMember` relationships are used to link test result `Observations` to the associated test group `Observation`.
* Multiple levels of test group `Observations` and test result `Observations` may be nested to support complex report structures, such as those used in Microscopy, Culture and Sensitivity (MC&S) reports.
* `ServiceRequest` is used to carry summary details relating to the test request that the test report was based on.
* If multiple tests or test groups are requested as part of the same “event” (generally by the same practitioner at the same time for the same subject), an instance of `ServiceRequest` is required for each requested test or test group. `ServiceRequest.requisition` acts as a common identifier to link the requests.
* The `Specimen.request` data element is used to reference the `ServiceRequest` that a specimen relates to. This should be used when a test was requested before the specimen was collected. 
* It is also possible to link a `ServiceRequest` to a specimen using the `ServiceRequest.specimen` data element. This should be used when a test is requested and the specimen has already been collected.

The following simplified data model illustrates the key aspects of this design approach for an example test report:

{{render:path-data-model-HbA1c-and-serum-lipid-levels-report}}

<br>
Further example test reports (with accompanying data models) are provided in the {{pagelink:R4Examples}}.