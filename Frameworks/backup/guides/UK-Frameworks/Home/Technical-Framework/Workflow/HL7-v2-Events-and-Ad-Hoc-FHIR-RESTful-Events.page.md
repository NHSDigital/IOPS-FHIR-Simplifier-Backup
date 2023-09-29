## {{page-title}}

The mappings to FHIR are indicative and would follow [FHIR Workflow Ad Hoc Communication - Option A: Simple RESTful POST or PUT](https://hl7.org/fhir/R4/workflow-ad-hoc.html#optiona)

See also [NHS England Interoperability Handbook - Message Broker](https://www.england.nhs.uk/wp-content/uploads/2017/03/interoperabilty-handbk.pdf)


 {{render:diagrams-TechnicalFramework-Workflow-ResourceMessageBroker}} 
 
In HL7 v2, the message broker is normally called a **Trust Integration Engine (TIE)**

NHS England specifications for HL7 v2 ADT 

- [NHS England HL7 V2 ADT Message Specifications](https://raw.githubusercontent.com/NHSDigital/IOPS-Frameworks/main/documents/HSCIC%20ITK%20HL7%20V2%20Message%20Specifications.pdf)

{{render:diagrams-TechnicalFramework-Workflow-Hl7v2Example}}

NHS England specifications for HL7 FHIR RESTful Ad Hoc 

- [Electronic Referral System (eRS)](https://digital.nhs.uk/developer/api-catalogue/e-referral-service-fhir) 

### Admission, Discharge and Transder (ADT)


| Event Code |Description | Event | Request |FHIR Resource | 
|-- 
| A28 |Create/Register Patient | &check; | |   Patient (POST)|
| A31 | Update Patient demographics| &check; | |   Patient (PUT)
|A01 | Patient admitted (inpatient)| &check; | |   Encounter (POST)
|A02 | Patient transferred (between wards)| &check; | |   Encounter (POST)
|A03 | Patient discharged| &check; | |   Encounter (POST)
|A04 | Patient visit (inc arrival for appointment)| &check; | |   Encounter (POST)
|A05 | Pre Admission (inpatient) or Planned Appointment (outpatient)Encounter / | &check; | |   Appointment (POST)
|A08 | Patient visit update | &check; | |   Encounter (PUT)
|A11 | Cancel Admission| &check; | |   Encounter (DEL)
|A12 | Cancel Transfer| &check; | |   Encounter (DEL)
|A13 | Cancel Admission| &check; | |   Encounter (DEL)

### Other

| Group | Event Code |Description | Event | Request |FHIR Resource | 
|-- 
| ORM/OMG/ORU/OM1| R01 | Observation Message |  &check;  || DiagnosticReport (POST) <br/> Observation (POST) <br/> Binary (POST)|
| ORM/OMG/ORU/OM1|O01 | Order (diagnostic test, referral or prescription)|  |&check; |ServiceRequest / MedicationRequest (POST)
| REF | I12 | Referral |  | &check;| ServiceRequest (POST) |
| MDM | T01 | Document Notification |&check; |  | DocumentReference (POST) |
| MDM |T02 | Document Notification and content | &check;|  | Binary (POST) <br/>  DocumentReference (POST) | 
| MDM |T03 / T04 / T07 / T08 / T09 / T10 | Document Notification Update (more fine grained) |&check; |  | DocumentReference (PUT) |