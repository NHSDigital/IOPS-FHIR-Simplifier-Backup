## {{page-title}}

There are three ways an API consumer may access the GP system supplier's APIs. They differ in the identity provider used and the routing to the API:

1. Use NHS login for identity and route API requests through APIM.
1. Use NHS login for identity and make API requests directly against the GP system's APIs.
1. Use another trusted identity provider and make API requests directly against the GP system's APIs.

{{render:api-access-approaches.png}}

Option 1 (using NHS login and routing requests through APIM) is fully supported by NHS England and is a minimum that must be made available and supported for consumers of the APIs. It provides the following benefits:

- provides central oversight and standards provided by NHS England
- provides visibility and metrics to NHS England
- suppliers can leverage the expertise of NHS England to aid trouble shooting and dealing with security
- low burden for consumers, no need to know which GP system is being called (as details are handled by NHS England)
- low burden for GP supplier (only a single origin to be trusted), no need to be open to the world, can leverage the third party accreditation process used by NHS login
- NHS England provides the first line of defence against abuse and misuse, reducing burden on supplier to a minimum

Options 2 and 3 are currently out of scope of this guide and are listed to highlight how consumers and GP supplier systems can interact without the need for NHS England to be involved. Providing alternative mechanisms to access APIs helps to encourage experimentation and innovation.