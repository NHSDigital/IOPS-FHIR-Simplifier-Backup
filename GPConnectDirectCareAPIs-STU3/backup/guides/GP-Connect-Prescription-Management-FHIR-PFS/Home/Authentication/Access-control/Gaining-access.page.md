## {{page-title}}

There are a number of measures in place to control access to the PFS APIs when they are accessed through APIM.

1. The client application e.g. [NHS App](https://www.nhs.uk/nhs-app/) must be registered and assured with [NHS login](https://nhsconnect.github.io/nhslogin/). This allows the client app to use NHS login for patient identity and acquire an ID Token during the login process
1. The client application must be registered with the APIM platform
1. The client application must be known to and assured by the GP system
1. The patient must have a [high level verification (P9)](https://nhsconnect.github.io/nhslogin/user-journeys/#p9) on their NHS login account
1. The patient must be registered on the GP system they are associated to in [PDS](https://digital.nhs.uk/services/demographics) (accessed via [PDS FHIR API](https://digital.nhs.uk/developer/api-catalogue/personal-demographics-service-fhir))

Patients are identified in requests to the GP system through an NHS login ID token. Requests to the GP system made through APIM go through a process called {{pagelink:token-exchange}}.