---
topic: InformationModel
---
### Information Model
The following diagram is a high-level logical representation of the key business entities that this specification is based on:

{{render:path-diagram-information-model}}

<br>

To aid clarity, individual and organisation type entities (e.g. Performer / Performing Organisation) have been combined in the diagram but may be referenced independently. Each business entity is described below:

| Entity Name | Description |
|--
| Test Request Summary | A summary of the original test request that is returned with the **Test Report**. |
| Specimen | Details relating to the specimen(s) provided for testing. |
| Test Report | The overall findings and clinical interpretation relating to one or more pathology tests or investigations. The report may reference individual **Test Results**, **Test Groups** or a combination of these. |
| Test Group | A set of related tests, for example a Full Blood Count. **Test Groups** are often referred to as batteries, panels or profiles. Multiple levels of **Test Groups** and **Test Results** may be nested to support complex report structures, such as those used in Microscopy, Culture and Sensitivity reports. Refer to the design guidance for {{pagelink:DesignRelatedTests}} for further information.|
| Test Result | A single test result. Includes the name and associated SNOMED CT code for the test (e.g. “Glucose substance concentration in plasma” – 1110521000000108) and the result, with an accompanying unit of measure where appropriate (e.g. 4.8 mmol/L). |
| Patient | Demographics and other administrative information relating to a patient. |
| Requester / Requesting Organisation | Details relating to the individual and/or organisation that requested a pathology test. |
| Specimen Collector / Specimen Collecting Organisation | Details relating to the individual and/or organisation that collected a specimen. |
| Performer / Performing Organisation | Details relating to the individual and/or organisation that performed a pathology test. |

<br>

#### Information Model to FHIR Profile Mapping
The following is a list of the business entities with a link to the associated profile descriptions that are included in the specification:

| Entity Name | Profile Name |
|--
| Test Request Summary | {{pagelink:R4ServiceRequest}} |
| Specimen | {{pagelink:R4Specimen}} |
| Test Report | {{pagelink:R4DiagnosticReport}} |
| Test Group | {{pagelink:R4ObservationTestGroup}} |
| Test Result | {{pagelink:R4ObservationTestResult}} |
| Patient | {{pagelink:R4Patient}} |
| Requester | {{pagelink:R4Practitioner}} |
| Requesting Organisation | {{pagelink:R4Organization}} |
| Specimen Collector | {{pagelink:R4Practitioner}} |
| Specimen Collecting Organisation | {{pagelink:R4Organization}} |
| Performer | {{pagelink:R4Practitioner}} |
| Performing Organisation | {{pagelink:R4Organization}} |

<br>

Refer to the {{pagelink:DesignDataMapping}} section of the specification for a detailed definition of the mapping between the data items associated with each business entity and the corresponding FHIR data elements.

<br>