# {{page-title}}

## Overview
The UK Core will conform to the <a href="https://build.fhir.org/conformance-rules.html">FHIR Standard</a>. Conformance applies to the UK Core itself and also to assets derived from UK Core where conformance to UK Core is claimed or required.


## What Should Conform? 
Implementers should create an implementation guide which follows the HL7 UK process for creating implementation guides and it will either contain FHIR assets which are valid constrained (derived) versions of the FHIR UK Core FHIR assets or use the UK Core assets as they stand. In reality most implementations will be a mixture of UK Core assets and locally derived FHIR assets. The local implementation guide and locally created FHIR assets SHOULD follow the same rules as documented in this implementation guide. Extension of the UK Core is allowed by any local implementation using the <a href="https://www.hl7.org/fhir/r4/extensibility.html" target="_blank">extension method</a> defined by the FHIR standard. When a implementer extends the UK Core the following considerations should be made:

- Extensions to the UK Core SHOULD be fed back to the UK Core Development Team for review and possible inclusion in the UK Core (these may be rejected the use case is too specific and not therefore suitable for use across the UK) and then will be just local extensions.
- Extensions to the UK Core SHALL be correct usage of FHIR.
- Extensions SHALL NOT be created to circumvent UK Core constraints.
- Where there is a HL7 common extension that is suitable it SHALL be used.    

Conformance is the term used in FHIR to denote:

- an implementation guide's adherence to the underlying FHIR specification.
- an implementation's adherence to an implementation guide.

To enable this, the FHIR specification describes the structure and behaviour of an API or data exchange using a set of resource definitions and a selected FHIR data exchange paradigm. These are described below.

Implementation Guides group and present the relevant resource and framework information, and explanatory material, as it applies in a specification domain.

Implementations asserting conformance to UK Core claim that:

- data exchanged conforms to the UK Core specified structure or is a valid constraint.
- data values conform to the specified UK Core ValueSets where binding is "required", and to their data type constraints.
- data is exchanged in a manner conformant to the selected exchange paradigm, and to the constraints on the interactions defined within that paradigm.

Implementations claiming conformance to UK Core SHOULD be able to validate their conformance using a suitable FHIR validator and the UK Core packages.See the {{pagelink:Validation-of-implementations}} section for further information. There are also guidance pages that contain constraints and business rule that are not computable, these SHALL be met to be UK Core conformant.

### Definitional / Conformance resources

FHIR defines data structure, data content and interface behaviour as a set of computable definitional resources. These are presented with additional explanatory and overview material as an Implementation Guide.

#### Data model and structure

- [CapabilityStatement](https://www.hl7.org/fhir/r4/capabilitystatement.html) - Lists which StructureDefinitions are used in the API
- [StructureDefinition](https://www.hl7.org/fhir/r4/structuredefinition.html) - Defines how a particular structure (Resource profile, Extension) is used:
    - Describes how existing elements in resources are used
    - Defines extensions that can be used in resources (or data types)
    - Defines cardinalities for existing elements, e.g. mandatory elements or those that are not used
    
#### Data content model

- [ValueSet](http://hl7.org/fhir/r4/valueset.html), [CodeSystem](http://hl7.org/fhir/r4/codesystem.html) - Defines use of terminology or structured data within the API
    - Defines standard and custom terminologies used
    - Defines which codes to use for a particular coded element (by specifying which to use in a particular Resource profile)
- [ConceptMap](http://hl7.org/fhir/r4/conceptmap.html) - Maps between local and standard terminologies or content models
- [NamingSystem](http://hl7.org/fhir/r4/namingsystem.html) - Registers system namespaces for identifiers and terminologies


### Behaviour

- [CapabilityStatement](http://hl7.org/fhir/r4/capabilitystatement.html) - Defines which interactions are supported within the API and provides additional details about how API calls are used
- [OperationDefinition](http://hl7.org/fhir/r4/operationdefinition.html) - Define additional or custom operations not in the base FHIR specification
- [SearchParameter](http://hl7.org/fhir/r4/searchparameter.html) - Adds additional search parameters not in the base FHIR specification

### Exchange Paradigms

FHIR offers several different approaches to exchange information. APIs pick which is most appropriate. Within API Management we aspire to use RESTful APIs as our default

- [RESTful API](http://hl7.org/fhir/r4/http.html) - a general-purpose interface supporting Search, Create, Read, Update and Delete interactions (with support for custom operations) over http.
- FHIR's RESTful API is opinionated, for example around http call content and syntax, in order to achieve consistent interoperability across diverse systems.
- [Messaging](http://hl7.org/fhir/r4/messaging.html) - FHIR supports message-based exchange, particularly event messaging. A message is formed as a message bundle of a MessageHeader resource and other relevant informational FHIR resources. Messages can be used with RESTful interactions, but tend to use a $process-message operation and define their request-response behaviour via the CapabilityStatement.
- [Documents](http://hl7.org/fhir/r4/documents.html) - A document is a coherent, immutable set of healthcare information, formed as a composition of relevant FHIR resources. Documents are authored and attested, and should have a consistent presentation. Document exchange tends to use service-oriented exchange patterns, but may be used RESTfully.
- [Services](http://hl7.org/fhir/r4/services.html) - FHIR resources can be exchanged using Service Oriented Architecture (SOA) exchange and integration patterns. These may be defined as OperationDefinitions.



---

