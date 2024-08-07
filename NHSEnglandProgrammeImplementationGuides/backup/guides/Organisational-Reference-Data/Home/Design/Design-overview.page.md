## {{page-title}}

<!-- <div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b> Important:</b> This page is under development by NHS England</div> -->

<!--The ORD FHIR API provides an R4 FHIR Application Programming Interface (API) to allow connecting systems to search and update ORD indicators.

- The API provides a [FHIR RESTful interface](https://hl7.org/fhir/R4/http.html) within which transactions are performed directly on the server resource using synchronous endpoints using GET, POST and PUT HTTP verbs.

- The API is intended to supersede the ORD FHIR DSTU2 API for common use cases.

- An ORD indicator has been modelled around a FHIR R4 Flag. Refer to - {{pagelink:Home/Design/Data-mapping.page.md}}. 

- The API will allow a healthcare professional to query, add and remove a ORD indicator. Refer to - {{pagelink:Home/Design/Interactions.page.md}}. 

- As a pre-requisite for calling the ORD FHIR R4 API , client systems MUST have traced the patient on PDS to ensure they have the correct NHS number for the patient. The <a href='https://developer.nhs.uk/apis/spine-core/pds_overview.html'>Spine Core API spec</a> outlines the approaches available for this demographic trace.

- The ORD FHIR R4 API will be hosted on the NHS England API Platform. Refer to - {{pagelink:Home/Build/Authentication.page.md}}. -->


# Design overview

The Organisational Data Service (ODS) FHIR API, using the FHIR R4 standard, allows connecting systems to request and receive organisational related data. The FHIR API is read-only and so connecting systems can not update or delete data but only request data.

## Design

Connecting systems will interact with the ODS FHIR API using the below endpoint pattern:

GET [base]/organisation-data-terminology-api/fhir

The value of [base] will be dependent on which system environment the FHIR API exists in. The variances are:

Integration environment
https://int.api.service.nhs.uk/organisation-data-terminology-api/fhir

Sandbox environment
https://sandbox.api.service.nhs.uk/organisation-data-terminology-api/fhir

Production environment
https://api.service.nhs.uk/organisation-data-terminology-api/fhir

## Modelling

The ODS FHIR API has been modelled in such a way as to ensure all previously used data fields within the ODS domain are mappable to the modelled FHIR assets. Click [here] to view the data mapping.

## Interactions

Based on the use cases stated within the NHS England IG Clinical and Technical Assurance Sprint 2 Documentation Pack for the ODS FHIR API, previously named as Organisation Reference Data (ORD), the design of the ODS FHIR API is intended to support the following interactions:

- A Data Manager requests data for reporting requirements
- A Clinical Systems Developer requests data for integration with downstream systems
- A Commissioner requests data for payment requirements
- A Head Clinician requests data for research and forecasting
- A Data Consumer requests data for data source updates
- A National Payments System requests data for payment requirements
