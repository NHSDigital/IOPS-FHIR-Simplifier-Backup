# Authentication

  <div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b> Important:</b> This page is under development by NHS England</div>

## Security and authorisation
The FGM-IS FHIR R4 API  will be hosted on the <a href='https://digital.nhs.uk/services/api-platform'>NHS England API Platform</a> which will provide the necessary <a href='https://digital.nhs.uk/developer/guides-and-documentation/security-and-authorisation#top'>Security and Authorisation</a>.

In order to be able to make API calls into Spine for the FGM-IS FHIR R4 API in a live (or path-to-live) Spine environment, clients first need to go through a <a href='https://digital.nhs.uk/developer/guides-and-documentation/digital-onboarding'>digital onboarding</a> process with NHS England.

After completing this onboarding process, the supplier of the calling system will be provided with an ASID (Accredited System ID) to use to identify the calling system in Spine calls. This must be used in all calls into the API.

<br>

## Passing system and user context into FGM-IS API calls
To support audit and provenance within the Spine, the information about both the calling system and the authenticated user MUST be passed into FGM-IS FHIR R4 API calls. The audit / provenance information needed by the FGM-IS FHIR R4 API is:

- ASID (calling system)
- Source practitioner (including SDS id)
- Role of source practitioner (SDSRoleProfileId / JobRoleCode) 

The above will be captured in header parameters on the API calls:

- Authorization = Bearer &lt;jwt_token_string&gt;
- NHSD-Session-URID  =  &lt;healthcare worker role ID&gt;

For example, information passed in the form of an OAuth Access (bearer) token - specifically an encoded JSON web token can be found in the <a href='https://developer.nhs.uk/apis/spine-core/security_jwt.html'>Spine Core API spec</a>.

