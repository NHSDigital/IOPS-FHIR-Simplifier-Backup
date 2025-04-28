## {{page-title}}

To Search for an Endpoint you can search for it directly, or by referencing it's Organization.

{{tree:http://hl7.org/fhir/StructureDefinition/Endpoint,buttons}}

### Search by Endpoint

Endpoint.identifier

Definition: Identifier for the organization that is used to identify the endpoint across multiple disparate systems.

Invocations

[base]/Endpoint?identifier=[system]|[value]

{{xml:http://hl7.org/fhir/SearchParameter/Endpoint-identifier}}

### Search by Endpoint Organization
Endpoint.managingOrganization

Definition: The organization that manages this endpoint (even if technically another organization is hosting this in the cloud, it is the organization associated with the data).

Invocations

[base]/Endpoint?organization=Organization/[id]

{{xml:http://hl7.org/fhir/SearchParameter/Endpoint-organization}}

{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Organization, buttons}}

### Search by Organization Endpoint
Organization.endpoint

Definition: Technical endpoints providing access to services operated for the organization.

Invocations
[base]/Organization?endpoint=Endpoint/[id]

{{xml:http://hl7.org/fhir/SearchParameter/Organization-endpoint}}

Invocations
[base]/Organization?identifier=[system]|[value]

{{xml:http://hl7.org/fhir/SearchParameter/Organization-identifier}}
