## {{page-title}}

  <div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b> Important:</b> Work in progress.</div>

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>User Storey</strong>: 
  Svetlana's GP had to cancel a prescription they had sent to EPS. A pharmacy had already downloaded the prescription, so the cancel could not be actioned immediately.  Rather implementing MESH for the Subsequent Cancellation response, the GP wishes to check the current status of the prescription on demand.
</div>

EPS Prescription Tracker is currently available in two forms: 

- [EPS Prescription Tracker](https://digital.nhs.uk/services/electronic-prescription-service/about-the-eps-prescription-tracker) An application available on N3/HSCN.
- [EPS Prescription Tracker API](https://digital.nhs.uk/services/electronic-prescription-service/guidance-for-developers/guidance-for-developers-ideas-for-using-the-prescription-tracker-api) An API available on N3/HSCN.

### FHIR Task

EPS NextGen will be adding a new Prescription Tracker API.

| FHIR Exchange | API | FHIR Resource Profile | 
|--
| FHIR RESTful  | <a href="https://digital.nhs.uk/developer/api-catalogue/electronic-prescription-service-fhir#api-Tracker">GET /Task?</a> | {{pagelink:NHSDigital-Task-duplicate-2}} | 

#### Search Parameters

See [Task - Search Parameters](https://simplifier.net/guide/DigitalMedicines/NHSDigital-Task#search)