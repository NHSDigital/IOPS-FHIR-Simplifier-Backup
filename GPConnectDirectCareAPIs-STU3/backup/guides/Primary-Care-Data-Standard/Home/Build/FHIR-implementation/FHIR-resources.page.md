## {{page-title}}

### Resource data types

The FHIR specification defines a set of [data types](https://www.hl7.org/fhir/STU3/datatypes.html) that are used for the resource elements.

The user locale (that is, user’s language, region and any special variant preferences that the user may want to see in their user interface) of a system SHALL NOT affect the FHIR on the wire representation of any data types (especially date-time and number formats).

Certain aspects of [primitive data type](https://www.hl7.org/fhir/STU3/datatypes.html#primitive) representation warrant further consideration and SHALL be taken into consideration when designing and constructing FHIR resources.

For example:

- leading 0 digits are not allowed
- strings SHALL NOT exceed 1MB in size
- URIs are case sensitive
- UUID values (urn:uuid:53fefa32-fcbb-4ff8-8a92-55ee120877b7) use all lower case
- dates have no time zone
- dates can be partial dates (for example, just ‘year’ or ‘year + month’)
- precision of the decimal value has significance
- primitive types other than string SHALL NOT have leading or trailing whitespace
- [use of null](https://www.hl7.org/fhir/STU3/json.html#null) and empty / zero length values in [XML and JSON representations](https://www.hl7.org/fhir/STU3/datatypes.html#1.19.0.1.1)

### Resource narrative

The FHIR [resource narrative](https://www.hl7.org/fhir/STU3/narrative.html) is not currently expected to be populated.

### Resource references

The FHIR resource model includes [resource references](http://hl7.org/fhir/STU3/references.html) from one resource to another.

A reference can be either:

- a relative or absolute URL to a resource managed by the same resource server (a local reference), or
- an absolute URL to a resource managed by another resource server (a remote reference)

A provider’s ability to process a request relating to a resource may depend on its ability to utilise one or more resource references that the resource contains (for example, its ability to ‘follow the links’ to other resources).

### Resource metadata

Servers SHALL provide the `profile` [metadata](https://www.hl7.org/fhir/STU3/resource.html#Meta) for each resource, asserting that the content conforms to one of the GP Connect resource profiles.

Servers SHALL provide the `version Id` metadata for each item. This SHALL change each time the content of the resource changes.

Consumer creating or amending a resource SHALL provide the `profile` metadata details within the sent resource. The `profile` metadata should be checked for by the provider to ensure predictable process and for forward compatibility when a server can handle multiple profiles for the same type of resource.

Clients SHALL use the `version Id` when performing updates to allow [management of resource contention](https://www.hl7.org/fhir/STU3/http.html#concurrency) and to protect against [lost updates](http://www.w3.org/1999/04/Editing/).

### Resource transactions

When performing an update or creating [resource transactions](https://www.hl7.org/fhir/STU3/http.html#transactional-integrity), servers:

- SHALL **validate the content against valid profiles** and business rules before creating/updating the resource
- MAY apply business rules that alter the content
- MAY merge updated content with existing content

Servers SHALL validate the existence of any referenced resources when creating or updating a resource. For example, a `Slot` reference (for example, `Slot/D497DB00-99AA-11E5-A837-0800200C9A66`) used when creating a new `Appointment` would be checked for existence on the server and an error returned (and the create interaction aborted) if the slot does not exist.

Refer to the GitHub hosted [GP Connect FHIR repository](https://github.com/nhsconnect/gpconnect-fhir) for the published FHIR profiles.

Refer to the [HL7® FHIR® Validator](https://www.hl7.org/fhir/STU3/validation.html#jar) page for the most up to date details on how FHIR resources can be validated.

Servers SHALL provide a read interaction for every resource it accepts update interactions on.

Consumers SHALL follow the pattern described in the [Transactional Integrity](https://www.hl7.org/fhir/STU3/http.html#transactional-integrity) section of the base FHIR specification, built on top of version-aware updates, for updating resources.

---