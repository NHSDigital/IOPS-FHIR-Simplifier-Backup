## {{page-title}}

### PDS
You need to be able to provide a verified NHS number to use an API. You can do this using a Spine accredited system, a Demographics Batch Service (DBS) batch-traced record (CSV), or using a Spine Mini Services Provider (HL7v3).

### SDS / ODS
To resolve a given GP Practice organisation to its URI you need to be able to do a Spine SDS query (LDAP) using the practice’s ODS code to perform an SDS End Point Lookup.

### FHIR
In order to be a compliant FHIR server, provider systems need to expose a valid FHIR [CapabilityStatement](https://www.hl7.org/fhir/STU3/capabilitystatement.html) profile.

Refer to **Development Guidance - FHIR API Guidance - Common API Guidance [this link needs updating]** for full details on the common FHIR API patterns used throughout all the GP Connect APIs.