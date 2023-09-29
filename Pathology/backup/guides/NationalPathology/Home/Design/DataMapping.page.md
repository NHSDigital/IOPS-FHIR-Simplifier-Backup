---
topic: DataMapping
---
## Data Mapping

These pages provide mapping of the business entities and data to FHIR resources. the constrains that need to be applied to each FHIR resource using the UK Core profiles is provided on the indiviual profile pages which are linked from each mapping section.

## Pathology Reporting Data Mapping

|Business Entity Name|Source Data Item Name|Cardinality|FHIR Target Mapping          |Notes|
|--|--|--|--|--|
|**TestRequestSummary**||||Contains a summary of the original test request|
|TestRequestSummary|Identifier|1..1|ServiceRequest.identifier|A business level identifier for the original test request.Set by the requesting organisation|
|TestRequestSummary|Status|1..1|ServiceRequest.status|The status of the original test request|
|TestRequestSummary|Intent|1..1|ServiceRequest.intent|Indicates whether the request is a proposal, plan, an original order or a reflex order|
|TestRequestSummary|Request Date and Time|0..1|ServiceRequest.authoredOn|The date and time of the test request|
|TestRequestSummary|Urgency|0..1|ServiceRequest.priority|The urgency of the test request.|
|TestRequestSummary|Requested Tests|0.*|ServiceRequest.code|The tests that have been requested|
|TestRequestSummary|Request Reason|0..1|ServiceRequest.reasonCode|The tests that have been requested|
|TestRequestSummary|Condition(s)|0..*|ServiceRequest.reasonReference|A reference to any conditions the patient has (as supplied by the requester) that are relevant to the test request|
|TestRequestSummary|Notes|0..1|ServiceRequest.note|Notes relating to the test request, as provided by the requester. May be used to provide further clinical context and/or the reason for requesting the tests|
|TestRequestSummary|Requester|1..1|ServiceRequest.requester|Reference to the person and/or organisation that requested the tests|
|TestRequestSummary|Patient|1..1|ServiceRequest.subject|Reference to the patient that the tests are for|
|**Specimen**||||Contains information on the specimen that was provided for testing. Where a single type of specimen (for example blood) is split into multiple containers it is treated as multiple specimens|
|Specimen|Identifier|1..1|Specimen.identifier|A business level identifier for the specimen supplied by the collecting/requesting organisation e.g. GP Practice|
|Specimen|Accesson Identifier|1..1|Specimen.accessionIdentifier|A business level identifier for the specimen supplied by the performing organisation e.g. laboratory performing the test|
|Specimen|Status|0..1|Specimen.status|The status of the specimen|
|Specimen|Type|0..1|Specimen.type|The kind of material that forms the specimen|
|Specimen|Received Date and Time|0..1|Specimen.receivedTime|The date and time that the specimen was received for processing|
|Specimen|Collection Date and Time|0..1|Specimen.collection.collected|The date and time that the specimen was collected from the patient|		
|Specimen|Collected Specimen Quantity|0..1|Specimen.collection.quantity.value|The quantity of specimen collected|	
|Specimen|Collected Specimen Quantity|0..1|Specimen.collection.quantity.unit|The name and code of the unit of measure associated with the specimen quantity|
|Specimen|Body Site|0..1|Specimen.collection.bodySite|The anatomical site of the specimen collection|
|Specimen|Fasting Status|0..1|Specimen.collection.fastingStatus.</br>fastingStatusCodeableConcept|Details of the fasting status of the patient|
|Specimen|Notes|0..1|Specimen.note|Notes relating to the specimen|
|Specimen|Patient|1..1|Specimen.subject|Reference to the patient from which this specimen was taken|
|Specimen|Specimen Collector|0..1|Specimen.collection.collector|Reference to the person and/or organisation that collected the specimen|
|**Test Group**||||Refers to a group of related diagnostic tests, for example a Full Blood Count. Test groups are often referred to as batteries, panels or profiles. The individual tests within a test group may differ between organisations. |	
|Test Group|Identifier|1..1|Observation.identifier|A business level identifier for the test group|
|Test Group|Status|1..1|Observation.status|The status of the test group.|
|Test Group|Name|1..1|Observation.code|The name and code of the test group|	
|Test Group|Notes|0..1|Observation.comment|Notes relating to the test group, as provided by the performing organisation|
|Test Group|Result(s)|0..*|Observation.related|References to the results that make up this test group|
|Test Group|Patient|0..1|Observation.subject|Reference to the patient that this test group relates to|
|Test Group|Specimen|0..1|Observation.specimen|Reference to the specimen on which these results were based|
|Test Group|Performer|0..*|Observation.performer|Reference to the person and/or organisation that authored the test report|	
|**Test Result**||||Contains information relating to a diagnostic test result. It is populated by the performing organisation|
|Test Result|Identifier|1..1|Observation.identifier|A business level identifier for the test result|	
|Test Result|Status|1..1|Observation.status|The status of the test result|	
|Test Result|Category|0..1||The general type of test result|	
|Test Result|Test Performed Date and Time|0..1|Observation.effectiveDateTime|The date and time that the test was performed|
|Test Result|Test Result Issued Date and Time|0..1|Observation.issued|The date and time that the test result was issued to the requesting organisation|
|Test Result|Test Name|1..1|Observation.code|The name and code of the test that was performed|
|Test Result|Test Result Value|0..1|Observation.value.valueQuantity.value|The test result value|
|Test Result|Test Result Value Comparator|0..1|Observation.value.valueQuantity.comparator|A comparator that may used to indicate whether the actual value is greater or less than the stated value|	
|Test Result|Test Result Value Unit of Measure|0..1|Observation.value.valueQuantity.unit|The name and code of the unit of measure associated with the test result value|
|Test Result|Test Result Absent Reason|0..1|Observation.dataAbsentReason|The reason why a test result is missing|	
|Test Result|Reference Range Low|0..1|Observation.referenceRange.low|The reference range low value|
|Test Result|Reference Range High|0..1|Observation.referenceRange.high|The reference range high value|
|Test Result|Reference Range Text|0..1|Observation.referenceRange.text|A human readable text-based description to provide additional information about the reference range. For example, the target population that the reference range applies to and/or differences based on factors such as age or sex|
|Test Result|Body Site|0..1|Observation.bodySite|The body part that was tested/observed|	
|Test Result|Test Method|0..1|Observation.method|The method of testing/observation that was used|	
|Test Result|Clinical Summary|0..1|Observation.comment|A human readable text-based clinical interpretation of the test result and any additional notes provided by the performing organisation|
|Test Result|Interpretation Code|0..1|Observation.interpretation|A simple coded interpretation of the test result, for example "out of range", "high", "low"|
|Test Result|Patient|0..1|Observation.subject|Reference to the patient that this result is about|
|Test Result|Performer|0..1|Observation.performer|Reference to the person and/or organisation that authored the test report|	
|Test Result|Specimen|0..1|Observation.specimen|Reference to the specimen on which these results were based|	
|Test Result|Parent Test Group|0..1|Observation.related|Reference to the test group header if the result is part of a test group|
|**Test Report**||||Contains the overall findings and clinical interpretation of one or more diagnostic test results. A test report may reference individual tests, test groups or a combination of these|
|Test Report|Identifier|1..1|DiagnosticReport.identifier|A business level identifier for the test report. Set by the performing organisation|
|Test Report|Status|1..1|DiagnosticReport.status|The status of the test report|
|Test Report|Clinical Discipline|0..1|DiagnosticReport.category|The clinical discipline or diagnostic service that created the test report|
|Test Report|Report Name|0..1|DiagnosticReport.code|A name that describes the test report. May be a clinical code and/or text|
|Test Report|Issued Date and Time|1..1|DiagnosticReport.issued|The date and time that the test report was issued by the performing organisation|
|Test Report|Clinical Summary|0..1|DiagnosticReport.conclusion|A human readable text-based clinical summary relating to the test report and any additional notes provided by the performing organisation|
|Test Report|Clinical Finding Code|0..1|DiagnosticReport.codedDiagnosis|A coded clinical finding of the test report|
|Test Report|Request Reference|0..*|DiagnosticReport.basedOn|Reference to the Test Request Summary|	
|Test Report|Patient|1..1|DiagnosticReport.subject|Reference to the patient that this report relates to|	
|Test Report|Performer|0..*|DiagnoticReport.performer|Reference to the person and/or organisation that authored the test report|	
|Test Report|Specimen|0..*|DiagnoticReport.specimen|Reference to details about the specimen(s) this report is based on|
|Test Report|Result|0..*|DiagnoticReport.result|Reference to the result(s)/result groups contained in the report|
|**Patient**||||The subject of the clinical tests|
|Patient|NHS number|0..1|Patient.identifier|The unique identifier for a patient within the NHS in England and Wales|
|Patient|Other Identifier(s)|0..*|Patient.identifier|Country specific or local identifier e.g. Community Health Index (CHI) in Scotland.|
|Patient|Family Name|1..1|Patient.name(official).family|That part of a person's name which is used to describe family, clan, tribal group, or marital association|							
|Patient|First Given Name|1..1|Patient.name(official).given|The first forename or given name of a person|
|Patient|Other Given Name(s)|0..*|Patient.name(official).given|The middle name(s) or other given name(s) of a person|
|Patient|Name Prefix|0..1|Patient.name(official).prefix|The name prefix (e.g. title) of a person|
|Patient|Stated Gender|0..1|Patient.gender|A person’s stated gender. This is self-declared or inferred by observation for those unable to declare their own|
|Patient|Date of Birth|0..1|Patient.birthDate|The date on which a person was born or is officially deemed to have been born|
|Patient|Ethnicity|0..1|Patient.extension (ethnicCategory)|The ethnicity of a person, as specified by the person|
|Patient|Usual Address|0..1|Patient.address|The patient’s usual place of residence|
|Patient|Primary Telephone Number|0..1|Patient.telecom|The primary telephone number of the patient|
|Patient|Primary Email Address|0..1|Patient.telecom|The primary email address of the patient|
|Patient|Named GP|0..1|Patient.generalPractitioner|Reference to the patient's named primary care provider|
|Performer||||The person that authored the test report|
|Performing|Organization|||The organization that authored the test report.|
|Requester||||The person that requested the clinical tests|
|Requesting Organization||||The organization that requested the clinical tests.	|				
|Specimen|Collector|||The person that collected the specimen|
|Specimen|Collecting Organization|||The organisation that collected the specimen|							



