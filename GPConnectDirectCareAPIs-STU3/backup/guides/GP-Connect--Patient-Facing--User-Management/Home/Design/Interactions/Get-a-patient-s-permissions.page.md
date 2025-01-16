## {{page-title}}

Get a patient's permissions, from the perspective of a patient facing application e.g. the NHS App can be used to fulfil two main use cases:

1. To provide the information to the patient so they can see what permissions they have to their medical record and access to services.
2. For the application to determine which features and functionality within the application should be displayed and made available to the patient. For example, if the patient has `view` access (and by implication doesn't have manage access) to the appointments service there would be no point in displaying buttons to book or cancel appointments.

{{render:get-patient-permissions-sequence.png}}

For more detailed information see:

- [Get a patient's permissions (NHS Digital API catalogue)](https://digital.nhs.uk/developer/api-catalogue/gp-connect-patient-facing-user-permissions#api-Default-getPatientPermissions)
- {{pagelink:Home/Build/How-to-get-a-patient-s-permissions}}

### Enabling online access for a first-time user

The act of using the get permissions API will enable online access and set a patient's default permissions the first time the request is made. This is detailed in the [new online patient access](../Design/New-online-patient-access?version=current) page.

As a result, all applications using the PFS APIs should call the get permissions API prior to any other interactions. If this doesn't happen there is a chance the patient will not have online access enabled and the expected API response will return a not found error.