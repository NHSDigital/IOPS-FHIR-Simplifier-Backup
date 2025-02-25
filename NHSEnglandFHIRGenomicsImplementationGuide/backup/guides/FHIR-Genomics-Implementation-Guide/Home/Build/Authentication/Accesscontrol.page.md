## {{page-title}}

In Genomics, users may need to request or contribute to genomic testing while acting in multiple roles, e.g. by specialty/organization. Granular controls for restricting users to specific test types or test requests have been found to be difficult to implement. Local providers have thus opted to use broad access controls to separate users who are involved in genomics testing and those who are not.

Requirements elicitation has found that constraining access to test requests by organization, where the user is logged in, is a reasonable approach. Where there are users who work at multiple organisations, they should only see test requests and tasks for the organisation they are logged in to. 

Further access controls could be implemented if a requirement arises to restrict things further, by adding additional claims to the access token passed in by the requesting system.

Access control is expected to match controls in place for existing national services, users will be expected to authenticate via the national care identity service (CIS2). 

Suppliers will be expected to onboard onto the service through NHS England's API onboarding service.

## Portal Authentication

CIS2 is the preferred authentication mechanism for national services and enables a number of different mechanisms to authenticate in a secure manner. More details about the service can be found on the [NHS England Care Identity Authentication pages](https://digital.nhs.uk/services/identity-and-access-management/nhs-care-identity-service-2/care-identity-authentication)

Users can currently authenticate using any of the following five options:
- Windows Hello for Business
- Security Keys
- iPad App
- Microsoft Authenticator
- Smartcards

The expected users of the national portal may be technically immature organisations and will only require infrequent access to the service, but the expectation is that they will be able to use one of the authentication mechanisms available
within CIS2.

**Note:** For each of the authentication mechanisms, there is restrictions about device versions, setup and access controls which needs to be taken into consideration when onboarding services, details can be found on the [CIS2 guidance for Registration Authorities](https://digital.nhs.uk/services/care-identity-service/applications-and-services/care-identity-management/user-guides/managing-non-smartcard-authenticators)

## API Authentication/Authorization

The API will support two types of authentication for systems directly integrated with the service:

1. Where a user is present the user should be authenticated using CIS2 and the token should be passed through with the request, as is specified for the portal requirement above.
2. Where the request is being made in an unattended scenario, such as a system polling to see if new tasks have been created for them, the API will support application level authentication.

The API-M layer will manage general access to the API for both user and application level authentication, but the signed token for both types of authentication will be passed through to the service, where we can apply additional authorization based on claims within the token if we need to. This is the same model used by services such as NRL FHIR R4 APIs.

### User Authentication

CIS2 is the preferred user authentication mechanism for accessing national services, both from an authentication perspective as well as an audit perspective. 

The user’s authentication token will need to be sent with the request to the API and will contain claims which represent their access permissions.

The Genomic Medicine Service will expect clients to follow the [National RBAC guidance for developers](https://digital.nhs.uk/developer/guides-and-documentation/security-and-authorisation/national-rbac-for-developers) when registering and authorising users.

### Application Authentication

For unattended API calls, application level authentication using APIGEE OAuth2.0 capability within API-M will be used. This mechanism is currently being used for other national services such as NRL FHIR R4. Information for integration with this service is available on the [NHS England developer guidance pages](https://digital.nhs.uk/developer/guides-and-documentation/security-and-authorisation/application-restricted-restful-apis-signed-jwt-authentication)

The connecting system will need to get a signed token and pass it to the genomics test order API with their request. The token will be passed from the API-M layer back to the Genomics services where the service will use the claims in the token to apply appropriate access controls. For the alpha the access controls within API-M which control access to the API as a whole will be sufficient to meet the requirements, but the service will need to process the token for audit purposes and possibly additional access controls in beta and further development phases.

### Purpose-Based Access Control

Within the Unified Genomic Record, there is a need to restrict access to particular aspects of a patient's genetic profile, or family linkage, based on a user's role, the purpose for which they are accessing the data, the activities they are performing (e.g. CRUD operations) and the patient's own consent. 

This work is currently in discovery to elicit concrete requirements of how these access controls need to be represented, as well as how the claims themselves are represented and tested before providing access to a UGR record. 

It is expected the framework will align to [IHE PCF](https://profiles.ihe.net/ITI/PCF/), with consent representing the patient's own directives and security tags representing an overall level of sensitivity of classes of information.

The particular representation of claims is pending investigation but it is expected these will align somewhat to OpenID Connect or OAuth2. At the present time, there is no NHS England service which is able to support Attribute-Based Access Control (required to represent activities/purposes being performed by the user).

The level of granularity the consent and PBAC policies will need to support, e.g. Classes of resources, specific instances or specific attributes within those instances, is also pending investigation.