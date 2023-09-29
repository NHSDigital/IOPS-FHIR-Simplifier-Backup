## {{page-title}}

  <div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b> Important:</b> This page is under development by NHS England</div>

The CP-IS FHIR API provides an R4 FHIR Application Programming Interface (API) to allow connecting systems to search for and read CP-IS indicators.

- The API provides a [FHIR RESTful interface](https://hl7.org/fhir/R4/http.html) within which interactions are performed directly on the server resource using synchronous endpoints using the GET HTTP verb.

- The API is intended to supersede the existing [CP-IS HL7v3 API](https://digital.nhs.uk/developer/api-catalogue/child-protection-information-sharing-hl7-v3) for use cases where Scheduled and Unscheduled Care Settings need to access Child Protection information.

### Design 

Compared to the HL7v3 API, the interface definition of Child Protection - Information Sharing looks very different under the FHIR ReST paradigm.

API calls to the resource Endpoints are patterned:

```GET [base]/CPIS/[resource]?patient=[NHSNumber]```

with Headers:

The Base URL, ```[base]```, will be:

| Environment | [base] |
|--|--|
| Sandbox |            https://sandbox.service.nhs.uk/cpis/FHIR/R4 |
| Integration test |   https://int.api.service.nhs.uk/cpis/FHIR/R4 |
| Production |         https://api.service.nhs.uk/cpis/FHIR/R4 |


### Modelling

- CP-IS information has been modelled as ... - {{pagelink:Home/Design/Data-mapping.page.md}}. 

### Interactions

- The API will allow a healthcare professional to query CP-IS information. Refer to - {{pagelink:Home/Design/Interactions.page.md}}. 

### Pre-requisites

- As a pre-requisite for calling the CP-IS FHIR R4 API , client systems MUST have traced the patient on PDS to ensure they have the correct NHS number for the patient. The <a href='https://developer.nhs.uk/apis/spine-core/pds_overview.html'>Spine Core API spec</a> outlines the approaches available for demographic trace and verification.

- CP-IS FHIR R4 API client systems SHALL implement [National role-based access control (RBAC)](https://digital.nhs.uk/developer/guides-and-documentation/security-and-authorisation/national-rbac-for-developers).

- The CP-IS FHIR R4 API will be hosted on the NHS England API Platform. The security and authorisation approach defined on page {{pagelink:Home/Build/Authentication.page.md}} SHALL be required. 