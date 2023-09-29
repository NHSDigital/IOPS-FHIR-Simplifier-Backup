## {{page-title}}

### Purpose
Elements are included for the billing approach, TAT/SLA tracking and prioritisation.
To confirm validity of urgency and apply lower level prioritisation. To know which test has been requested, which further tests are required within this request and how many patients are being tested within this request.

### Notes
Mapped to ServiceRequest, extensions are still in review. CI and CITT codes for genomic tests are pending addition to SNOMED-CT

### Mapping
| Source Data item | Target FHIR Element | HL7v2.5.1 Mapping | Description 
|--|--|
|Test request - Test request id|ServiceRequest.identifier|ORC-2|Unique id to identify this test request.|
|Test request - Payment status|ServiceRequest.extension:coverage|IN1-15|How the test request is funded. The current ValueSet for this field needs expansion, pending finalization of the MDS|
|Test request - Date and time request sent|ServiceRequest.authoredOn|ORC-9|Date and time the test request was made.|
|Test request - Is urgent|ServiceRequest.priority|TQ1-9|Confirmation if the test request is urgent.|
|Test request - Urgency reason|ServiceRequest.extension:priorityReason|N/A could possibly use TQ1-10|If urgent, the test request urgency reason.|
|Test request - Test Directory version|Inferred though version included in system URL, ServiceRequest.code.coding.system|OBR-4.3|The version of Test Directory the requested CI/CITT code relates to.|
|Test request - CI code|ServiceRequest.code|OBR-4|The code which identifies the requested test. Provided by Test Directory.|
|Test request - CITT code|ServiceRequest.code|OBR-4|The code (including decimal) which identifies the requested test. Provided by Test Directory.|
|Test request - CI code for multipurpose CITT|ServiceRequest.orderDetail|NTE segment attached to OBR|The code which identifies the test to be actioned when the CITT code is multipurpose.|
|Test request - Reason for testing|ServiceRequest.reasonCode|ORC-16|The reason for a genomic test.|
|Test request - Reason for reanalysis|Additional ServiceRequest.reasonCode/reasonReference elements|OBR-13 segment linked to ORC|The reason for a genomic test.|
|Test request - Detail of reason for reanalysis|ServiceRequest.supportingInfo elements|NTE segments linked to OBR segment for reanalysis reason|The detail associated to the reason reanalysis has been requested.|
|Test request - Type of reanalysis|ServiceRequest.orderDetail|Additional NTE segments attached to OBR|The type of reanalysis which has been requested.|
|Test request - DNA storage information|ServiceRequest.orderDetail|Additional NTE segments attached to OBR|If the reason for testng is DNA storage, this captures further detail.|
|Test request - Patient set to be tested|N/A - Determined through number of ServiceRequests in the test order|N/A - determined through number of ORC segments within OML^O21 message|Confirmation if the test is a singleton, duo or trio.|
|Test request - Count of patients to be tested|N/A - Determined through number of Patients referenced in ServiceRequests in test order|N/A - determined through number of PID segments referenced from ORC segments within OML^O21 message|Count of patients to be tested.|
|Test request - Date report required by|ServiceRequest.occurenceDateTime|OBR-8|The date a completed genomic report is required by.|
|Test request - Further information|ServiceRequest.supportingInfo|Additional segments attached to ORC/OBR|Further information regarding the test request.|

<!--
| Source Data item | Non WGS Rare Disease | Non WGS Cancer | WGS Rare Disease | WGS Cancer | Target FHIR Element | HL7v2.5.1 Mapping | Description 
|--|--|
|Test request - Funding|Mandatory|Mandatory|Mandatory|Mandatory|ServiceRequest.extension:coverage|IN1-15|How the test request is funded, NHS or privately.|
|Test request - Date and time|Mandatory|Mandatory|Mandatory|Mandatory|ServiceRequest.authoredOn|ORC-9|Date and time the test request was made.|
|Test request - Is urgent|Mandatory IF|Mandatory IF|Mandatory IF|Mandatory IF|ServiceRequest.priority|TQ1-9|Confirmation if the test request is urgent.|
|Test request - Urgency reason|Mandatory IF|Mandatory IF|Mandatory IF|Mandatory IF|ServiceRequest.extension:priorityReason|N/A could possibly use TQ1-10|If urgent, the test request urgency reason.|
|Test request - CI code|Mandatory|Mandatory|Mandatory|Mandatory|ServiceRequest.code|OBR-4|The code which identifies the requested test. Provided by Test Directory.|
|Test request - CITT code|Optional|Optional|Optional|Optional|ServiceRequest.code|OBR-4|The code (including decimal) which identifies the requested test. Provided by Test Directory.|
|Test request - Additional CITT codes to be tested|Optional|Optional|Mandatory IF|N/A|ServiceRequest.orderDetail|Additional OBR segments (OBR-4)|Further test codes applied to this request.|
|Test request - Singleton/Duo/Trio|Mandatory|N/A|Mandatory|N/A|N/A - Determined through number of ServiceRequests in the test order|N/A - determined through number of ORC segments within OML^O21 message|Confirmation if the test is a singleton, duo or trio.|
-->