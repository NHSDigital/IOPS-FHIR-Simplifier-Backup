## {{page-title}}

  <div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b> Important:</b> This page is under development by NHS England</div>

The CP-IS FHIR API provides an R4 FHIR Application Programming Interface (API) to allow connecting systems to search and read CP-IS indicators.

- The API provides a [FHIR RESTful interface](https://hl7.org/fhir/R4/http.html) within which interactions are performed directly on the server resource using synchronous endpoints using GET, POST and PUT HTTP verbs.

- The API is intended to supersede the existing [CP-IS HL7v3 API](https://digital.nhs.uk/developer/api-catalogue/child-protection-information-sharing-hl7-v3 for a care setting) for use cases where Scheduled and Unscheduled Care Settings need to access Child Protection information.

### Modelling

- CP-IS information has been modelled as ... - {{pagelink:Home/Design/Data-mapping.page.md}}. 

### Interactions

- The API will allow a healthcare professional to query CP-IS information. Refer to - {{pagelink:Home/Design/Interactions.page.md}}. 

### Pre-requisites

- As a pre-requisite for calling the CP-IS FHIR R4 API , client systems MUST have traced the patient on PDS to ensure they have the correct NHS number for the patient. The <a href='https://developer.nhs.uk/apis/spine-core/pds_overview.html'>Spine Core API spec</a> outlines the approaches available for this demographic trace.

- The CP-IS FHIR R4 API will be hosted on the NHS England API Platform. Refer to - {{pagelink:Home/Authentication/Index.page.md}}. 