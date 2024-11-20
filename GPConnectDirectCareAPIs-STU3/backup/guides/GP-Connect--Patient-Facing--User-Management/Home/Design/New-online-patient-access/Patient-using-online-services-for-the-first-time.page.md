## {{page-title}}

When a patient accesses online services for the first time at a GP practice they need to have online access activated.

GP system suppliers using the GP System Integration called [IM1](https://digital.nhs.uk/services/gp-it-futures-systems/im1-pairing-integration) achieve this through a feature called linkage keys which are handled as part of the [NHS login](https://nhsconnect.github.io/nhslogin/gp-credentials/) process.

GP Connect PFS has simplified the process and does not require linkage keys. When a patient is authenticated through NHS login to a [high level verification (P9)](https://nhsconnect.github.io/nhslogin/user-journeys/#p9) and makes a request to the PFS APIs they will have online access enabled by the GP supplier system if they do not already. The details of how that happens are visualised in the following sequence diagram.

{{render:patient-validation-sequence.png}}

The diagram shows how a patient facing application (e.g. the NHS App) uses NHS login as the identity provider for a patient and communicates with the Foundation System's PFS APIs via the API Management platform (APIM).

When the request from APIM arrives at the Foundation System the first action is for the Foundation System's authorisation server to validate the NHS login ID token with NHS login (ensuring the token is valid and for a P9 verified patient) and return an access token for that patient to APIM. APIM will then continue to make the request it was originally called with to the PFS API using the Foundation System's access token. This process should happen for every PFS API, effectively providing APIM with an access token for each API.

Currently there are four APIs:

- [GP Connect (Patient Facing) User Permissions API](https://digital.nhs.uk/developer/api-catalogue/gp-connect-patient-facing-user-permissions)
- [GP Connect (Patient Facing) Access Record - FHIR API](https://digital.nhs.uk/developer/api-catalogue/gp-connect-patient-facing-access-record-fhir)
- [GP Connect (Patient Facing) Appointment Management - FHIR API](https://digital.nhs.uk/developer/api-catalogue/gp-connect-patient-facing-appointment-management-fhir)
- [GP Connect (Patient Facing) Prescriptions - FHIR API](https://digital.nhs.uk/developer/api-catalogue/gp-connect-patient-facing-prescriptions-fhir)

When the API to [get a patient's permissions](https://digital.nhs.uk/developer/api-catalogue/gp-connect-patient-facing-user-permissions#api-Default-getPatientPermissions) is called the Foundation System should run through the following logic and activities:

{{render:patient-validation-flow.png}}

- validate the patient exists in the GP system
- check if the patient has online access enabled
    - if they do - return the patient's existing permissions
    - if they do not - check if the patient is flagged as 'at risk'
	    - if they are - set the patient's permissions as appropriate for an at risk patient (determined by the practice), enable online access and return the patient's permissions
	    - if they are not - set the patient's default permissions (using the practice's default permissions), enable online access and return the patient's permissions

### Note on request sequencing

A consumer application must call the get permissions API before it calls any other API. This is to ensure that the Foundation System enables online access for the patient (if the patient does not already have online access enabled). If a request is made to another PFS API and the patient doesn't have online access enabled the API will respond with an appropriate response such as `Not Found` to which the consumer application should deal with as appropriate.
