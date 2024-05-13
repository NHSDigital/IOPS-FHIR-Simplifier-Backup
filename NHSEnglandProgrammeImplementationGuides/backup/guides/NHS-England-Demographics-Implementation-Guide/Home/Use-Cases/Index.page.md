## {{page-title}}

Insert content for developers and technical architects here 

Content is currently on [Confluence](https://nhsd-confluence.digital.nhs.uk/pages/viewpage.action?pageId=768054103)

{{render:demographics-pathway}}

<plantuml>
@startuml
 
 
title Patient Administration
 
 
:Find Patient;
if (Patient Found?) is (found) then
: Update Patient (if required) ;
: Merge Patient (if required);
else
  if (Additional details required?) is (yes) then
    :Patient Registration Form ;
    :Create Patient;
  else
    :Create Patient;
  endif
endif
 
@enduml
</plantuml>

### Actors

- **Patient Demographics Consumer** A 3rd party system or application which is a client to a source of patient demographics such as an
  - Patient Administration System (PAS)
  - Electronic Patient Record (EPR)
  - Master Patient Index (MPI) e.g. Personnel Demographics Service (PDS)
- **Patient Identity Source** A source system of patient demographics such as a PAS, EPR, MPI or PDS. Systems such as MPI or PDS may also be
  - **Patient Identity Registry** a master patient index of patient demographics and identity.
- **Patient Identity Consumer** A client system to Patient Identity Source and/or Patient Identity Registry such as a Electronic Document Management System (EDMS/XDS), Laboratory Information Management System (LIMS), etc. These systems do not normally manage patient demographics.


### FHIR API

All interactions are [RESTful](https://hl7.org/fhir/R4/http.html) unless stated otherwise.

### Related Specifications

| Implementation Guides |
|--
| [Patient Demographics Query for mobile (PDQm) - IHE](https://profiles.ihe.net/ITI/PDQm/) |
| [Structured Data Capture (SDC) - HL7 FHIR](https://build.fhir.org/ig/HL7/sdc/) |
| [FHIR Workflow](https://hl7.org/fhir/R4/workflow-module.html) 

### API Specifications

 - {{pagelink:Home/FHIR-Assets/CapabilityStatement/Patient-Demographics-Service-PDS-API.page.md}}
 - {{pagelink:Home/FHIR-Assets/CapabilityStatement/National-Proxy-Service-API.page.md}}
 
