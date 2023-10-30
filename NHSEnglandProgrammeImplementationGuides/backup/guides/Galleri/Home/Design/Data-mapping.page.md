## {{page-title}}
    
  <div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b> Important:</b> This page is under development by NHS England</div>
 

| Source Data item               | Cardinality |Target FHIR Element                 | Notes         
|--|--|
|report.company|1..1|Organization.id<br/>Organization.name|ODS should be used for identifier & name, using the system "https://fhir.nhs.uk/Id/ods-organization-code"
|report.product|1..1|ServiceRequest.code|This will be a fixed value<br/>system "http://snomed.info/sct"<br/>code "1148754001"<br/>display "Screening for neoplasm"
|report.template|1..1|###|
|report.creationDateTime|1..1|DiagnosticReport.issued|Using the appropriate [dateTime](http://hl7.org/fhir/datatypes.html#dateTime) format
|report.reportType|1..1|###|
|report.disclaimer|1..1|DiagnosticReport.conclusion|A fixed disclaimer string
|patient.participantId|1..1|Patient.identifier|The patient identifier used by Grail<br/>system "https://grail.com/patient-id"
|patient.age|1..1|###|NOT CURRENTLY IN MESSAGE
|patient.biologicalSex|1..1|###|NOT CURRENTLY IN MESSAGE
|sample.orderingGrailId|1..1|Specimen.identifier|The speciment identifier used by Grail<br/>system "http://grail.com/grail-id"
|sample.sampleType|1..1|Specimen.type|A fixed value of<br/>system "http://snomed.info/sct"<br/>code "119297000"<br/>display "Blood specimen"
|sample.collectionDate|1..1|Specimen.collection.collectionDateTime|Using the appropriate [dateTime](http://hl7.org/fhir/datatypes.html#dateTime) format
|orderingProvider.fullName|1..1|Organization.name|ODS organization name NHS England. Name fixed to "NHS ENGLAND - X26"
|orderingProvider.credentials|1..1|###|
|orderingProvider.location|1..1|###|ODS organization address for NHS England. Address fixed to line "THE LEEDS GOVERNMENT HUB"<br/>line "7-8 WELLINGTON PLACE"<br/>city "LEEDS"<br/>postalCode "LS1 4AP"<br/>country "ENGLAND"
|testResult.cancerSignalResult|1..1|Observation.valueCodeableConcept.coding|The cancer signal result<br/>system "https://grail.com/test-result" code (one of) "CANCER_SIGNAL_DETECTED" | "NO_CANCER_SIGNAL_DETECTED" | "CANCELED" display (one of) "Cancer signal detected" | "No cancer signal detected" | "Cancelled"
|testResult.origin|0..1|Observation.###|
|testResult.secondOrigin|0..1|Observation.###|
|testResult.labComments|0..1|Observation.note.text|Of the grouper Observation
|lab.name|1..1|Organization.name|Name of Laboratory where the sample was processed
|lab.directorFullName|1..1|Organization.contact.name.text|Full name of the Laboratory director of the sample processing lab
|lab.directorCredentials|1..1|###|
|lab.cliaId|1..1|Organization.identifier|The system is fixed to "http://terminology.hl7.org/NamingSystem/CLIA"
|lab.capId|1..1|Organization.identifier|The system is fixed to "http://terminology.hl7.org/NamingSystem/CAP"
|lab.location|1..1|Organization.address|Address of the lab that performed the sample processing
|lab.phone|1..1|Organization.telecom|Using system "phone"
|lab.fax|1..1|Organization.telecom|Using system "fax"
|lab.email|1..1|Organization.telecom|Using system "email"
|attachment.data|1..1|DiagnosticReport.presentedForm.data|Attached pdf document in Base64
