# Introduction

## Update Record Vision

This specification enables the GP record to be updated directly from a patient/citizen interaction that took place outside of the GP service but within a care setting.  (For example a pharmacy or a specialised healthcare clinic).

FHIR Messaging components specified within this site have been developed by NHS Digital and use CareConnect profiles created in collaboration with the INTEROPen community.

The INTEROPen vision is to create a library of nationally defined HL7® FHIR® resources and interaction patterns that implementers can adopt to simplify integration and interoperability within England’s health and social care systems.

The vision for Update Record is to become the primary means of updating the patient record with structured data where it is appropriate to update the patient record. 

## Purpose 
The primary objective of this specification is to outline the mechanism for writing to a patient record within a GP system using the GP Connect data model. This capability allows the patients record to be updated using structured and coded data that is machine readable. Structured data allows the consuming system to import and process the data easily to help support healthcare professionals in the treatment of patients


## Scope
Update Record capability will support the ingestion of data from a number of different clinical areas. The initial release supports:

* Encounters
* Medications
* Observations

## FHIR version
Standard for Trial Use 3 (STU3) is the version of FHIR which has been utilised for the Update receord capability. 

---