## {{page-title}}

### Consumer

The consumer must make a request to [get a patient's permissions](https://digital.nhs.uk/developer/api-catalogue/gp-connect-patient-facing-user-permissions#api-Default-getPatientPermissions) prior to making any other PFS API requests. This ensures that the patient has online access enabled, see {{pagelink:Home/Design/New-online-patient-access}} for additional details.

### Supplier

The supplier must ensure the patient has online access enabled. This is performed during the authorisation process of the patient's request by the GP supplier system. See {{pagelink:Home/Design/New-online-patient-access}} for additional details.
