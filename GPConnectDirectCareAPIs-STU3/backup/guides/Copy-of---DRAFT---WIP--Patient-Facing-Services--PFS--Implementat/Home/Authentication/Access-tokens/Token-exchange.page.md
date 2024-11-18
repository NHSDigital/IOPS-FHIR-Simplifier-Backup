---
topic: token-exchange
---

## {{page-title}}

Token exchange is a process that happens within APIM. The client application (for example, NHS App) includes the patient's NHS login ID token in the request to the API which is proxied through APIM. APIM will use the NHS login ID token to acquire an access token for the GP system which will then be used in subsequent requests by APIM on behalf of the patient to the GP system.

The provider must have an OAuth 2.0 service available to handle the authentication and authorisation requests.

The NHS login ID and APIM access tokens both have a 60 minute validity period. Once a token has expired it can be refreshed using the standard OAuth refresh token flow.