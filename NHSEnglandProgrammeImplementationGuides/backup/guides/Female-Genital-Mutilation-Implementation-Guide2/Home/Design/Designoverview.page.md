## {{page-title}}

  <div markdown="span" class="alert alert-warning" role="alert"><i class="fas fa-exclamation-triangle"></i><b> Important:</b> This page is under development by NHS England</div>

The FGM-IS FHIR API provides an R4 FHIR Application Programming Interface (API) to allow connecting systems to search and update FGM-IS indicators.

- The API provides a [FHIR RESTful interface](https://hl7.org/fhir/R4/http.html) within which transactions are performed directly on the server resource using synchronous endpoints using GET, POST and PUT HTTP verbs.

- The API is intended to supersede the FGM FHIR DSTU2 API for common use cases.

- An FGM-IS indicator (family history of FGM) has been modelled around a FHIR R4 Flag. Refer to - {{pagelink:Home/Design/Data-mapping.page.md}}. 

- The API will allow a healthcare professional to query, add and remove a FGM-IS indicator. Refer to - {{pagelink:Home/Design/Interactions.page.md}}. 

- As a pre-requisite for calling the FGM-IS FHIR R4 API , client systems MUST have traced the patient on PDS to ensure they have the correct NHS number for the patient. The <a href='https://developer.nhs.uk/apis/spine-core/pds_overview.html'>Spine Core API spec</a> outlines the approaches available for this demographic trace.

- The FGM-IS FHIR R4 API will be hosted on the NHS England API Platform. Refer to - {{pagelink:Home/Build/Authentication.page.md}}. 