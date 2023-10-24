---
topic: Pre-Requisites for Acknowledegment Framework (FHIR R4 Implementation)
---
## Pre-Requisites for Acknowledgement Framework
### Requirements
•	SHALL support FHIR R4

•	SHALL implement R4  Sender and/or Receiver Responsibilities as per acknowledgement framework requirements.

•	The sending system SHALL populate Message Header <sender> with a reference to the sending [Organization](https://simplifier.net/packages/fhir.r4.ukcore.stu1/0.5.1/files/597362) within the relevant UK core resource that presents in the FHIR bundle.

•	Both sending and receiving system MUST populate Message Header<source.endpoint> with an actual message source or id

•	The event code MAY be populated according to the the [CodeSet](https://simplifier.net/hl7fhirukcorer4/ukcore-messageevent-duplicate-2)

