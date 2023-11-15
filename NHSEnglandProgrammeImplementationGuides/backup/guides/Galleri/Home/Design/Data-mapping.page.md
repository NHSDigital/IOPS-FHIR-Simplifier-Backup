## {{page-title}}
    
  <div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b> Important:</b> This page is under development by NHS England</div>
 

| Source Data item               | Cardinality |Target FHIR Element                 | Notes         
|--|--|
|report.company|1..1|Organization.id<br/>Organization.name|ODS should be used for identifier & name, using the system "https://fhir.nhs.uk/Id/ods-organization-code"
|report.product|1..1|ServiceRequest.code|A fixed value of<br/>system "http://snomed.info/sct"<br/>code "1148754001"<br/>display "Screening for neoplasm"
|report.creationDateTime|1..1|DiagnosticReport.issued|Using the appropriate [dateTime](http://hl7.org/fhir/datatypes.html#dateTime) format
|report.reportType|1..1|DiagnosticReport.code|A fixed value of<br/>system "http://snomed.info/sct"<br/>code "721981007"<br/>display "Diagnostic studies report"
|report.disclaimer|1..1|DiagnosticReport.conclusion|A fixed disclaimer string
|patient.participantId|1..1|Patient.identifier|The patient identifier used by the screening organisation
|patient.age|||NOT CURRENTLY IN MESSAGE
|patient.biologicalSex|||NOT CURRENTLY IN MESSAGE
|sample.orderingId|1..1|Specimen.identifier|The speciment identifier used by the screening organisation
|sample.sampleType|1..1|Specimen.type|A fixed value of<br/>system "http://snomed.info/sct"<br/>code "119297000"<br/>display "Blood specimen"
|sample.collectionDate|1..1|Specimen.collection.collectionDateTime|Using the appropriate [dateTime](http://hl7.org/fhir/datatypes.html#dateTime) format
|orderingProvider.fullName|1..1|Organization.name|ODS organization name NHS England. Name fixed to "NHS ENGLAND - X26"
|orderingProvider.credentials|1..1|Organization.identifier|A fixed value of<br/>system "https://fhir.nhs.uk/Id/ods-organization-code"<br/>value "X26"
|orderingProvider.location|1..1|Organization.address|ODS organization address for NHS England. Address fixed to line "THE LEEDS GOVERNMENT HUB"<br/>line "7-8 WELLINGTON PLACE"<br/>city "LEEDS"<br/>postalCode "LS1 4AP"<br/>country "ENGLAND"
|testResult.cancerSignalResult|0..1|Observation.valueCodeableConcept.coding|The cancer signal result<br/>system "https://grail.com/test-result" code (one of) "CANCER_SIGNAL_DETECTED", "NO_CANCER_SIGNAL_DETECTED" display (one of) "Cancer signal detected", "No cancer signal detected"
|testResult.origin|0..*|Observation.component.valueCodeableConcept|As part of the Observation for the primary site, that has an Observation.code.coding.display "Multi-cancer early detection predicted first cancer signal origin by machine learning-based classifier"<br/>See below for SNOMED CT [body site mapping](#BodySiteMap)
|testResult.secondOrigin|0..*|Observation.component.valueCodeableConcept|As part of the Observation for the primary site, that has an Observation.code.coding.display "Multi-cancer early detection predicted second cancer signal origin by machine learning-based classifier"<br/>See below for SNOMED CT [body site mapping](#BodySiteMap)
|testResult.labComments|0..1|DiagnosticReport.[extension-DiagnosticReport.note].valueAnnotation.text|An extension to hold lab comments
|lab.name|1..1|Organization.name|Name of Laboratory where the sample was processed
|lab.directorFullName|1..1|Organization.contact.name.text|Full name of the Laboratory director of the sample processing lab
|lab.directorCredentials|1..1|Organization.contact.name.text|As part of the Oragnization representing the performing lab
|lab.cliaId|1..1|Organization.identifier|The system is fixed to "http://terminology.hl7.org/NamingSystem/CLIA"
|lab.capId|1..1|Organization.identifier|The system is fixed to "http://terminology.hl7.org/NamingSystem/CAP"
|lab.location|1..1|Organization.address|Address of the lab that performed the sample processing
|lab.phone|1..1|Organization.telecom|Using system "phone"
|lab.fax|1..1|Organization.telecom|Using system "fax"
|lab.email|1..1|Organization.telecom|Using system "email"
|attachment.data|1..1|DiagnosticReport.presentedForm.data|Attached pdf document in Base64


## <a id="BodySiteMap"></a>Body site mapping to SNOMED CT

|Body Site|Description|SNOMED CT code 
|--|--| 
|ANUS|Anus|53505006 \| Anal structure 
|BLADDER_AND_UROTHELIAL|Bladder, Urothelial Tract|89837001 \| Urinary bladder structure <br/>57789003 \| Structure of urothelium
|SARCOMA|Bone and Soft Tissue|272673000 \| Bone structure <br/>87784001 \| Structure of soft tissue 
|BREAST|Breast|76752008 \| Breast structure
|CERVIX|Cervix|71252005 \| Cervix uteri structure
|COLON_RECTUM|Colon, Rectum|71854001 \| Colon structure <br/>34402009 \| Rectum structure 
|HEAD_AND_NECK|Head and Neck|69536005 \| Head structure <br/>45048000 \| Neck structure 
|KIDNEY|Kidney|64033007 \| Kidney structure 
|LIVER_BILEDUCT|Liver, Bile Duct|10200004 \| Liver structure <br/>28273000 \| Bile duct structure 
|LUNG|Lung|39607008 \| Lung structure 
|LYMPHOID_NEOPLASM|Lymphoid Lineage|414628006 \| Lymphoid neoplasm 
|MELANOMA|Melanocytic Lineage|1162635006 \| Malignant melanoma 
|MYELOID_NEOPLASM|Myeloid Lineage|414792005 \| Myeloid neoplasm 
|LUNG_NET_HG_NET|Neuroendocrine Cells of Lung or other Organs|127575007 \| Malignant neuroendocrine neoplasm, epithelial 
|OVARY|Ovary|15497006 \| Ovarian structure 
|PANCREAS_GALLBLADDER|Pancreas, Gallbladder|15776009 \| Pancreatic structure  <br/>28231008 \| Gallbladder structure
|PLASMA_CELL_NEOPLASM|Plasma Cell Lineage|127580003 \| Plasma cell neoplasm  
|PROSTATE|Prostate|41216001 \| Prostatic structure 
|UPPER_GI|Stomach, Oesophagus|69695003 \| Stomach structure <br/>32849002 \| Esophageal structure 
|THYROID|Thyroid Gland|69748006 \| Thyroid structure
|UTERUS|Uterus|35039007 \| Uterine structure

 