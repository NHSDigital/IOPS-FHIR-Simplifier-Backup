## {{page-title}}


### Ad Hoc Workflow Patterns

The simplest form of FHIR Workflow involves the POST of a `Request`, `Events` relating to the request are posted back. 

For Lab Results or Referrals this would be a `POST /ServiceRequest` for the request and `POST /DiagnosticReport` for the response. 

For more details see [FHIR Ad-Hoc Workflow Communication Patterns](http://hl7.org/fhir/R4/workflow-ad-hoc.html)

{{render:diagrams-workflow-traditional}}

Supporting information for the ServiceRequest or Observations relating to the DiagnosticReport would be shared via a `Query API` framework.

Standards in this guide to be used with this pattern are:

- {{pagelink:Home/Technical-Framework/Workflow/HL7-v2-Events-and-Ad-Hoc-FHIR-RESTful-Events.page.md}}
- {{pagelink:Home/Technical-Framework/Workflow/HL7-FHIR-Message-and-Documents--HL7-v3-and-CDA.page.md}}

### Workflow Management Patterns

**Ad Hoc workflow Patterns** lack support for clinical coordination and communication (see also {{pagelink:Home/Technical-Framework/Workflow/Workflow-Events.page.md}}. **Workflow Management Patterns** do and this includes direct activities relating to a referral such as rejection or referral acceptance, sub tasks such as booking an appointment relating to a referral.

For more details see [FHIR Workflow Mangement Patterns]( http://hl7.org/fhir/R4/workflow-management.html)

The following is an extract of the complete set of options.

#### Task Exchanges between Placer and Filler 

- [Option F: Creation of Task on placer's system](http://hl7.org/fhir/R4/workflow-management.html#optionf)
- [Option G: POST of Task to fulfiller's system](http://hl7.org/fhir/R4/workflow-management.html#optiong)

FOR Care Coordination elaboration (No broker)

{{render:diagrams-TechnicalFramework-Workflow-workflow-optiong}}

#### Task Exchanges via a Workflow Broker

- [Option H: POST of Task to a workflow broker](http://hl7.org/fhir/R4/workflow-management.html#optionh)

{{render:diagrams-TechnicalFramework-Workflow-workflow-optionh}}

NHS England Systems which follow this pattern are:

- [Electronic Prescription Service (EPS)](https://digital.nhs.uk/developer/api-catalogue/electronic-prescription-service-fhir) (HL7 FHIR Message R4)
- [Electronic Referral System (eRS)](https://digital.nhs.uk/developer/api-catalogue/e-referral-service-fhir) 