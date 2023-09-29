## {{page-title}}

The NHS login token includes an [`aud`](https://nhsconnect.github.io/nhslogin/scopes-and-claims/) claim which represents the partner service the token was granted to. This can be used to identify the client application the patient has authenticated with.
The `aud` claim provides the information the GP system needs in order to check the partner service is one they know and approve of and have assured. This should be used to determine what APIs and data the patient is able to access given the context in which they are accessing the information.
 
Currently the list of partner services and their identifiers is known only to NHS login. The information will be supplied to the GP system during the onboarding stages.