## {{page-title}}

This API is [user-restricted](https://digital.nhs.uk/developer/guides-and-documentation/security-and-authorisation#user-restricted-apis), meaning an end user must be present and authenticated to use it.

The end user must be:

- a patient
- authenticated with NHS login to [P9 identity verification level](https://nhsconnect.github.io/nhslogin/user-journeys/#p9)

The API uses [OpenID Connect](https://openid.net/connect/) to authenticate the end user and [OAuth 2.0](https://oauth.net/2/) to authorise the calling system. It supports the following security pattern using NHS login:

- [user-restricted RESTful APIs - NHS login separate authentication and authorisation](https://digital.nhs.uk/developer/api-catalogue/gp-connect-patient-facing-access-record-fhir#api-description__security-and-authorisation:~:text=User%2Drestricted%20RESTful%20APIs%20%2D%20NHS%20login%20separate%20authentication%20and%20authorisation)
