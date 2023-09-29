## {{page-title}}



## Security, authentication and authorisation

The CP-IS FHIR R4 API  will be hosted on the <a href='https://digital.nhs.uk/services/api-platform'>NHS England API Platform</a> which will provide the necessary <a href='https://digital.nhs.uk/developer/guides-and-documentation/security-and-authorisation#top'>Security, Authentication and Authorisation</a>.

In order to be able to make API calls into Spine for the CP-IS FHIR R4 API in a live (or path-to-live) Spine environment, clients first need to go through a <a href='https://digital.nhs.uk/developer/guides-and-documentation/digital-onboarding'>digital onboarding</a> process with NHS England.

After completing this onboarding process, the supplier of the calling system will be provided with an API Token to use to identify the calling system in Spine calls. This must be used in all calls into the API.

### User present access

- For User present access, API Consumer applications SHALL use the <a href='https://digital.nhs.uk/developer/guides-and-documentation/security-and-authorisation/user-restricted-restful-apis-nhs-cis2-separate-authentication-and-authorisation' class='external'>User-restricted RESTful APIs - NHS Care Identity Service 2 separate authentication and authorisation</a> pattern

- API Consumer applications using User-restricted RESTful APIs - NHS Care Identity Service 2 separate authentication and authorisation pattern SHOULD implement using the Standards-compliant approach defined in <a href='https://digital.nhs.uk/developer/guides-and-documentation/security-and-authorisation/user-restricted-restful-apis-nhs-cis2-separate-authentication-and-authorisation#step-9-determine-the-healthcare-worker-s-role' class='external'>Step 9: Determine the healthcare worker's role Section 2. Standards-compliant approach</a> 


### Unattended access

- Unattended access is NOT a suitable Authentication Authorisation pattern for healthcare applications accessing sensitive data.

<br>

## System and user context in CP-IS API calls

To support audit and provenance within the Spine, the information about both the calling system and the authenticated user MUST be available to the CP-IS FHIR R4 API application. 
- On calling the CP-IS FHIR R4 API, with a current access token, representing an authenticated, authorised User, CP-IS FHIR R4 API SHALL be able to infer Practitioner, PractitionerRole and represented Organization details of the User.

## Headers

To call the CP-IS FHIR R4 API, you need to include the following header in your call:

- Authorization = Bearer [access token]

See also
- {{pagelink:Home/Build/Headers.page.md}}


