---
topic: DesignBusinessIdentifiers
---
### Business Identifiers
Resources in National Pathology messages SHOULD be sent with appropriate Business Identifiers. The National Pathology messaging specification uses the DiagnosticReport, ProcedureRequest (in STU3), ServiceRequest (in R4), Specimen and Observation resources. These all SHOULD carry business identifiers to allow meaningful search, identification and linking to clinical context.

Business identifiers will consist of: a Naming System which identifies the identifier namespace an identifier string, which uniquely identifies the resource within that namespace

There is a preference hierarchy for business identifiers. These are described below, in order of preference:

#### National Identifiers
There is an existing set of identifier naming systems for Pathology resources - the HL7 OID identifiers for the PMIP project. These identifiers COULD be used, but are NOT recommended.

Provision of national Pathology business identifiers at a UK Core, or NHS England level is currently under investigation by HL7 UK and NHS England.

#### Local Identifiers
Where using a local business identifier, vendors and implementers SHOULD register a unique Naming System with HL7 UK. Within the Naming System, for each resource, implementers must generate an identifier string which uniquely identifies the resource within that namespace.

Recommendation: Use of properly registered local business identifier naming systems is the current recommended approach

A well-formed local identifier consists of: local naming system, claiming a URI namespace owned by the organisation identifier value, identifying a unique, persistent point within that namespace. An RFC4122 Universally Unique IDentifier (UUID) is a suitable implementation choice.

The identifier will appear as, for example:

```xml
<identifier>
	<system value="https://example.local.pathology.identifier/DiagnosticReport"/>
	<value value="52870765-6e68-4a33-b5a6-4bfeba94a187"/>
</identifier>
```
#### No Business Identifier available
Where no business identifier is available, caution must taken when presenting Test Report resources out of the overall Pathology message context. Where identification of a component resource is only by logical id cross reference, there is a significant risk of loss of clinical context.

---
