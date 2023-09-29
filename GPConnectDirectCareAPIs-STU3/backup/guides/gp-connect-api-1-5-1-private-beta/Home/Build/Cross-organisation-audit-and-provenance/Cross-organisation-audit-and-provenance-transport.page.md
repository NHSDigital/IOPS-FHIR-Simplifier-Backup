## {{page-title}}

### Bearer token
Consumer systems **SHALL** provide audit and provenance details in the HTTP ``` Authorization ```  header as an OAuth Bearer Token (as outlined in [RFC 6749](https://www.rfc-editor.org/rfc/rfc6749) in the form of a JSON Web Token (JWT) as defined in [RFC 7519](https://www.rfc-editor.org/rfc/rfc7519).

An example such an HTTP header is given below:
```
 Authorization: Bearer jwt_token_string 

```

Provider systems **SHALL** respond to OAuth Bearer Token errors in line with [RFC 6750 - section 3.1.](https://www.rfc-editor.org/rfc/rfc6750#section-3.1)

It is highly recommended that standard libraries are used for creating the JWT as constructing and encoding the token manually may lead to issues with parsing the token. A good source of information about JWT and libraries to use can be found on the [JWT.io site](https://jwt.io/)

### JWT generation
Consumer system **SHALL** generate a new JWT for each API request. The consumer generated JWT **SHALL** consist of three [base64url encoded](https://www.rfc-editor.org/rfc/rfc4648#section-5) parts separated by dots ., which are:

- header
- payload
- signature

#### Header
Consumer systems SHALL generate an unsecured JWT using the ‘none’ algorithm parameter in the header to indicate that no digital signature or MAC has been performed (please refer to section 6 of RFC 7519_ for details).
```
{
  "alg": "none",
  "typ": "JWT"
}
```
#### Payload
Consumers systems SHALL generate a JWT payload conforming to the requirements set out in the [JWT Payload](https://developer.nhs.uk/apis/gpconnect-1-5-0/integration_cross_organisation_audit_and_provenance.html#jwt-payload) section of this page.


#### Signature
Consumer systems **SHALL** generate an empty signature.

#### Complete JWT
The final output is three [base64url](https://tools.ietf.org/html/rfc4648#section-5) encoded strings separated by dots (note: there is some canonicalisation done to the JSON before it is base64url encoded, which the JWT code libraries will do for you).
```
eyJhbGciOiJub25lIiwidHlwIjoiSldUIn0.eyJpc3MiOiJodHRwOi8vZWMyLTU0LTE5NC0xMDktMTg0LmV1LXdlc3QtMS5jb21wdXRlLmFtYXpvbmF3cy5jb20vIy9zZWFyY2giLCJzdWIiOiIxIiwiYXVkIjoiaHR0cHM6Ly9hdXRob3JpemUuZmhpci5uaHMubmV0L3Rva2VuIiwiZXhwIjoxNDgxMjUyMjc1LCJpYXQiOjE0ODA5NTIyNzUsInJlYXNvbl9mb3JfcmVxdWVzdCI6ImRpcmVjdGNhcmUiLCJyZXF1ZXN0ZWRfcmVjb3JkIjp7InJlc291cmNlVHlwZSI6IlBhdGllbnQiLCJpZGVudGlmaWVyIjpbeyJzeXN0ZW0iOiJodHRwOi8vZmhpci5uaHMubmV0L0lkL25ocy1udW1iZXIiLCJ2YWx1ZSI6IjkwMDAwMDAwMzMifV19LCJyZXF1ZXN0ZWRfc2NvcGUiOiJwYXRpZW50LyoucmVhZCIsInJlcXVlc3RpbmdfZGV2aWNlIjp7InJlc291cmNlVHlwZSI6IkRldmljZSIsImlkIjoiMSIsImlkZW50aWZpZXIiOlt7InN5c3RlbSI6IldlYiBJbnRlcmZhY2UiLCJ2YWx1ZSI6IkdQIENvbm5lY3QgRGVtb25zdHJhdG9yIn1dLCJtb2RlbCI6IkRlbW9uc3RyYXRvciIsInZlcnNpb24iOiIxLjAifSwicmVxdWVzdGluZ19vcmdhbml6YXRpb24iOnsicmVzb3VyY2VUeXBlIjoiT3JnYW5pemF0aW9uIiwiaWQiOiIxIiwiaWRlbnRpZmllciI6W3sic3lzdGVtIjoiaHR0cDovL2ZoaXIubmhzLm5ldC9JZC9vZHMtb3JnYW5pemF0aW9uLWNvZGUiLCJ2YWx1ZSI6IltPRFNDb2RlXSJ9XSwibmFtZSI6IkdQIENvbm5lY3QgRGVtb25zdHJhdG9yIn0sInJlcXVlc3RpbmdfcHJhY3RpdGlvbmVyIjp7InJlc291cmNlVHlwZSI6IlByYWN0aXRpb25lciIsImlkIjoiMSIsImlkZW50aWZpZXIiOlt7InN5c3RlbSI6Imh0dHA6Ly9maGlyLm5ocy5uZXQvc2RzLXVzZXItaWQiLCJ2YWx1ZSI6IkcxMzU3OTEzNSJ9LHsic3lzdGVtIjoibG9jYWxTeXN0ZW0iLCJ2YWx1ZSI6IjEifV0sIm5hbWUiOnsiZmFtaWx5IjpbIkRlbW9uc3RyYXRvciJdLCJnaXZlbiI6WyJHUENvbm5lY3QiXSwicHJlZml4IjpbIk1yIl19fX0.

```

**Note:** the final section (the signature) is empty, so the JWT will end with a trailing . (this must not be omitted, otherwise it would be an invalid token)

### JWT payload
Consumers **SHALL** populate the payload section of the JWT with the following claims:

- iss (issuer)
- sub (subject)
- aud (audience)
- exp (expiry)
- iat (issued at)
- reason_for_request
- requested_scope
- requesting_device
- requesting_organization
- requesting_practitioner

Please see details below on how to populate each claim.

> Important: The JWT payload used in GP Connect API 0.x (DSTU2) is different to that displayed on this page. Please ensure you consult the relevant specification from the [GP Connect specifications](https://digital.nhs.uk/services/gp-connect/develop-gp-connect-services/specifications-for-developers) page when constructing the JWT for different GP Connect API major versions.

---


#### iss (issuer) claim

Consumer systems token issuer URI.

As the consuming system is presently responsible for generating the access token, this **SHALL** contain the URL of the Spine endpoint of the consumer system.

In future OAuth2 implementation, the ```iss``` claim will contain the URL of the OAuth2 authorisation server token endpoint.

**Example:** ``` "iss": "https://consumersupplier.thirdparty.nhs.uk/" ```

---

#### sub (subject) claim

ID for the user on whose behalf this request is being made. Matches [requesting_practitioner.id](https://developer.nhs.uk/apis/gpconnect-1-5-0/integration_cross_organisation_audit_and_provenance.html#requesting_practitioner-claim).

**Example:** ``` "sub": "10019" ```

---

#### aud (audience) claim

The service root URL of the provider system.

This is the value returned from the SDS endpoint lookup service in the nhsMhsEndPoint field.

**Example:** ``` "aud": "https://providersupplier.thirdparty.nhs.uk/GP0001/STU3/1" ```

---

#### exp (expiry) claim

Identifies the expiration time in UTC on and after which the JWT **SHALL NOT** be accepted for processing.

The expiration time **SHALL** be set to 5 minutes after the token creation time (populated in the iat claim).

The value must be an integer representing seconds past 01 Jan 1970 00:00:00 UTC, i.e. [UNIX time](https://en.wikipedia.org/wiki/Unix_time).

Providers **SHALL** reject requests with expired tokens.

Example: ``` "exp": 1469436987 ```

> Important: To ensure accuracy of timestamps, and minimise the likelihood of tokens being rejected due to clock skew providers and consumers SHALL synchronise their server clocks with NHS Network Time Protocol (NTP) servers.

---

#### requested_scope claim

The scope of the request.

Please the table below for which values to populate.

|Claim value | Description|When to use|
| ----------- | ----------- | ----------- |
| ```patient/*.read``` | 	Patient record read request | -[Find a patient](https://developer.nhs.uk/apis/gpconnect-1-5-0/foundations_use_case_find_a_patient.html)<br /> -[Read a patient](https://developer.nhs.uk/apis/gpconnect-1-5-0/foundations_use_case_read_a_patient.html)<br /> -[Retrieve a patient’s appointments](https://developer.nhs.uk/apis/gpconnect-1-5-0/appointments_use_case_retrieve_a_patients_appointments.html)<br /> -[Read an appointment](https://developer.nhs.uk/apis/gpconnect-1-5-0/appointments_use_case_read_an_appointment.html)<br /> -[Get patient’s structured record](https://developer.nhs.uk/apis/gpconnect-1-5-0/accessrecord_structured_development_retrieve_patient_record.html)<br /> -[Find a patient (Access Document)](https://developer.nhs.uk/apis/gpconnect-1-5-0/access_documents_use_case_find_a_patient.html)<br />-[Search for a patient’s documents](https://developer.nhs.uk/apis/gpconnect-1-5-0/access_documents_development_search_patient_documents.html)<br /> -[Retrieve a patient’s documents](https://developer.nhs.uk/apis/gpconnect-1-5-0/access_documents_development_retrieve_patient_documents.html)|
| ```patient/*.write``` | Patient record write request |-[Register a patient](https://developer.nhs.uk/apis/gpconnect-1-5-0/foundations_use_case_register_a_patient.html)<br />-[Book an appointment](https://developer.nhs.uk/apis/gpconnect-1-5-0/appointments_use_case_book_an_appointment.html)<br />-[Amend an appointment](https://developer.nhs.uk/apis/gpconnect-1-5-0/appointments_use_case_amend_an_appointment.html)<br />-[Cancel an appointment](https://developer.nhs.uk/apis/gpconnect-1-5-0/appointments_use_case_cancel_an_appointment.html) |
|```organization/*.read``` | Other read request |-[Get the capability statement](https://developer.nhs.uk/apis/gpconnect-1-5-0/foundations_use_case_get_the_fhir_capability_statement.html)<br />-[Find a practitioner](https://developer.nhs.uk/apis/gpconnect-1-5-0/foundations_use_case_find_a_practitioner.html)<br />-[Read practitioner](https://developer.nhs.uk/apis/gpconnect-1-5-0/foundations_use_case_read_a_practitioner.html)<br />-[Find an organisation](https://developer.nhs.uk/apis/gpconnect-1-5-0/foundations_use_case_find_an_organisation.html)<br />-[Read organisation](https://developer.nhs.uk/apis/gpconnect-1-5-0/foundations_use_case_read_an_organisation.html)<br />-[Read location](https://developer.nhs.uk/apis/gpconnect-1-5-0/foundations_use_case_read_a_location.html)<br />-[Search for free slots](https://developer.nhs.uk/apis/gpconnect-1-5-0/appointments_use_case_search_for_free_slots.html)<br />-[Get the capability statement (Access Record Structured)](https://developer.nhs.uk/apis/gpconnect-1-5-0/accessrecord_structured_get_the_fhir_capability_statement.html |
| ```organization/*.write``` | Other write request |(none currently) |


Providers should also read the associated [Security guidance](https://developer.nhs.uk/apis/gpconnect-1-5-0/development_api_security_guidance.html#authorisation-of-access-to-endpoints) in relation to this claim.

**Example:** ``` "requested_scope": "patient/*.read"	```	




