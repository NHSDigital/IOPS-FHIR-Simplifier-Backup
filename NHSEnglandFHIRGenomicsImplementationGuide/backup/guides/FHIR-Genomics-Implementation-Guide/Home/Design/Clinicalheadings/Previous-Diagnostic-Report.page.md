## {{page-title}}

### Purpose
To locate previous **Non-Genomic** diagnostic test reports linked to this service request.

### Notes
Mapped to DiagnosticReport.
Observations/test results within the DiagnosticReport are expected to be included as referenced Observation resources.
It is expected previous diagnostic reports will have a minimal amount of information coded for automated interpretation but reports can be attached as PDF documents or references to their location provided, as with Genomic reports.

### Mapping
| Source Data item | Target FHIR Element | HL7v2.5.1 Mapping | Description 
|--|--|
|Previous non genomic report - Report referral summary|DiagnosticReport.conclusion|OBX-5|Referring clinician's summary of the previous non genomic report to support test request.|
|Previous non genomic report - Report file/link|DiagnosticReport.presentedForm|OBX-5 where OBX-2=ED or RP|A copy of/or link to the previous non genomic report.|
|Previous non genomic report - Test performed date|DiagnosticReport.effectiveDateTime|OBX-19|The date a previous non genomic test was performed.|
|Previous non genomic report - Report identifier|DiagnosticReport.identifier|OBX-3|The identifier for the previous non genomic report.|
|Previous non genomic report - Test type|DiagnosticReport.code|OBR-4|A name that describes the previous non genomic report.|
|Previous non genomic report - Test result value comparator|DiagnosticReport.result( Observation.valueQuantity.comparator )|OBX-5|A comparator that may used to indicate whether the actual value is greater or less than the stated value. Applies to numeric values only.|
|Previous non genomic report - Test result value unit of measure|DiagnosticReport.result( Observation.valueQuantity.unit )|OBX-6|The name and code of the unit of measure associated with the test result value. Applies to numeric values only.|
|Previous non genomic report - Test result reference range low|DiagnosticReport.result( Observation.referenceRange.low )|OBX-7 (before operator)|The reference range low value.|
|Previous non genomic report - Test result reference range high|DiagnosticReport.result( Observation.referenceRange.high )|OBX-7 (after operator)|The reference range high value.|
|Previous non genomic report - Test result test method|DiagnosticReport.result( Observation.method )|OBX-17|The method of testing/observation that was used.|
|Previous non genomic report - Test result reference range text|DiagnosticReport.result( Observation.referenceRange.text )|OBX-7|A human readable text-based description to provide additional information about the reference range. For example, the target population that the reference range applies to and/or differences based on factors such as age or sex.|
|Previous non genomic report - Test result clinical summary|DiagnosticReport.result( Observation.interpretation )|OBX-8|A human readable text-based clinical interpretation of the test result and any additional notes provided by the performing organisation.|
|Previous non genomic report - Report result|DiagnosticReport.conclusionCode|OBR-5|Reference to the result(s)/result groups contained in the report.|
|Previous non genomic report - Report performer full name|DiagnosticReport.performer( PractitionerRole.practitioner( Practitioner.name ) )|OBX-16|The full name of the individual that authored the previous non genomic test report.|
|Previous non genomic report - Report performer organisation ODS code|DiagnosticReport.performer( PractitionerRole.organization( Organization.identifier ) )|OBX-23.10|The organisation ODS code of the individual that authored the previous non genomic test report.|
|Previous non genomic report - Original requester full name|DiagnosticReport.basedOn( ServiceRequest.requester( PractitionerRole.practitioner( Practitioner.name ) ) )|ORC-12|The full name of the individual that requested the previous non genomic test report.|
|Previous non genomic report - Original requester organisation ODS code|DiagnosticReport.basedOn( ServiceRequest.requester( PractitionerRole.organization( Organization.identifier ) ) )|ORC-21.10|The organisation ODS code of the individual that requested the previous non genomic test report.|
|Previous non genomic report - Original requester reason for request|DiagnosticReport.basedOn( ServiceRequest.reasonCode )|ORC-16|The reason for requesting the previous non genomic test report.|

