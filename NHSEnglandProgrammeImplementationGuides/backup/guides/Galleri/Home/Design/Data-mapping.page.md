## {{page-title}}
    
  <div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b> Important:</b> This page is under development by NHS England</div>
 

| Source Data item               | Cardinality |Target FHIR Element                 | Notes         
|--|--|
|Reporting Organisation|1..1|Organization.id<br/>Organization.name|ODS should be used for identifier & name, using the system "https://fhir.nhs.uk/Id/ods-organization-code"
|Requested Test|1..1|ServiceRequest.code|A fixed value of<br/>system "http://snomed.info/sct"<br/>code "1148754001"<br/>display "Screening for neoplasm"
|Repost Date|1..1|DiagnosticReport.issued|Using the appropriate [dateTime](http://hl7.org/fhir/datatypes.html#dateTime) format
|Report Type|1..1|DiagnosticReport.code|A fixed value of<br/>system "http://snomed.info/sct"<br/>code "721981007"<br/>display "Diagnostic studies report"
|Report Standard Text|1..1|DiagnosticReport.conclusion|A fixed disclaimer string
|Participant Identifier|1..1|Patient.identifier|The patient identifier used by the screening organisation
|Sample Identifier|1..1|Specimen.identifier|The speciment identifier used by the screening organisation
|Sample Type|1..1|Specimen.type|A fixed value of<br/>system "http://snomed.info/sct"<br/>code "119297000"<br/>display "Blood specimen"
|Sample Collection Date|1..1|Specimen.collection.collectionDateTime|Using the appropriate [dateTime](http://hl7.org/fhir/datatypes.html#dateTime) format
|Requesting Organisation Name|1..1|Organization.name|ODS organization name NHS England. Name fixed to "NHS ENGLAND - X26"
|Requesting Organisation Identifier|1..1|Organization.identifier|A fixed value of<br/>system "https://fhir.nhs.uk/Id/ods-organization-code"<br/>value "X26"
|Requesting Organisation Address|1..1|Organization.address|ODS organization address for NHS England. Address fixed to line "THE LEEDS GOVERNMENT HUB"<br/>line "7-8 WELLINGTON PLACE"<br/>city "LEEDS"<br/>postalCode "LS1 4AP"<br/>country "ENGLAND"
|Test Result (overall)|0..1|Observation.valueCodeableConcept.coding|The cancer signal result <br/>system "http://snomed.info/sct"<br/>See below for SNOMED CT [cancer signal result codes](#CancerSignalResult)
|Test Result Primary Site|0..*|Observation.component.valueCodeableConcept|As part of the Observation for the primary site, that has an Observation.code.coding.display "Multi-cancer early detection predicted first cancer signal origin by machine learning-based classifier"<br/>See below for SNOMED CT [body site mapping](#BodySiteMap)
|Test Result Secondary Site|0..*|Observation.component.valueCodeableConcept|As part of the Observation for the primary site, that has an Observation.code.coding.display "Multi-cancer early detection predicted second cancer signal origin by machine learning-based classifier"<br/>See below for SNOMED CT [body site mapping](#BodySiteMap)
|Lab Comments|0..1|DiagnosticReport.[extension-DiagnosticReport.note].valueAnnotation.text|An extension to hold lab comments
|Performing Lab Name|1..1|Organization.name|Name of Laboratory where the sample was processed
|Performing Lab Director Name|1..1|Organization.contact.name.text|Full name of the Laboratory director of the sample processing lab
|Lab Identifiers|1..1|Organization.identifier|Identifiers that the Lab has been assigned. These may be regulatory body identifiers that regulates labs testing human specimens
|Lab Address|1..1|Organization.address|Address of the lab that performed the sample processing
|Lab Contact Details|1..1|Organization.telecom|Using system "phone" for phone numbers, using system "fax" for fax numbers, using system "email" for email addressed
|Attachment|1..1|DiagnosticReport.presentedForm.data|Attached pdf document in Base64 that the Lab may provide


## <a id="BodySiteMap"></a>Body site mapping to SNOMED CT

|Body Site|SNOMED CT code 
|--|
|Anus|53505006 \| Anal structure 
|Bladder, Urothelial Tract|89837001 \| Urinary bladder structure <br/>57789003 \| Structure of urothelium
|Bone and Soft Tissue|272673000 \| Bone structure <br/>87784001 \| Structure of soft tissue 
|Breast|76752008 \| Breast structure
|Cervix|71252005 \| Cervix uteri structure
|Colon, Rectum|71854001 \| Colon structure <br/>34402009 \| Rectum structure 
|Head and Neck|69536005 \| Head structure <br/>45048000 \| Neck structure 
|Kidney|64033007 \| Kidney structure 
|Liver, Bile Duct|10200004 \| Liver structure <br/>28273000 \| Bile duct structure 
|Lung|39607008 \| Lung structure 
|Lymphoid Lineage|414628006 \| Lymphoid neoplasm 
|Melanocytic Lineage|1162635006 \| Malignant melanoma 
|Myeloid Lineage|414792005 \| Myeloid neoplasm 
|Neuroendocrine Cells of Lung or other Organs|127575007 \| Malignant neuroendocrine neoplasm, epithelial 
|Ovary|15497006 \| Ovarian structure 
|Pancreas, Gallbladder|15776009 \| Pancreatic structure  <br/>28231008 \| Gallbladder structure
|Plasma Cell Lineage|127580003 \| Plasma cell neoplasm  
|Prostate|41216001 \| Prostatic structure 
|Stomach, Oesophagus|69695003 \| Stomach structure <br/>32849002 \| Esophageal structure 
|Thyroid Gland|69748006 \| Thyroid structure
|Uterus|35039007 \| Uterine structure

## <a id="CancerSignalResult"></a>Cancer Signal Result

|SNOMED CT Code|Display
|--|
|TBC|Multi-cancer early detection signal detected
|TBC|Multi-cancer early detection signal not detected
