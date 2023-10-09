## Conformance

### Conformance to UK Core

The NHS England Implementation Guide conforms to FHIR UK Core STU3 0.0.6 but provides an additional layer of conformance for NHS England national programmes, products and systems to aid implementation where it is deemed appropriate by NHS England requirements. 

### Conforming to NHS England Implementation Guide (IG)

There are two different ways to implement NHS England IG:

1.	Profile Only Support: Local implementations **MAY** choose to support _only_ the NHS England Profiles to represent clinical information for local use only. 
2.	Profile Support & Interaction Support: NHS England Systems and Programs and local implementations that interact directly with national services or programmes **SHALL** support both the NHS England Profile content structure and the interaction patterns defined for a resource (or group of resources depending on the type of interaction) where there is additional guidance or conformance to FHIR UK Core stated within this IG. 

### Profile Only Support

Systems **MAY** deploy, and support, one or more NHS England profiles to represent clinical information. They are using the profile’s content model without any expectations to implement the NHS England interactions.

To support a NHS England profile, a server:

- **SHALL** be able to populate all Profile data elements that are mandatory and/or flagged as "Must Support" as defined by that Profile’s StructureDefinition.
- **SHOULD** declare support for a NHS England Profile by including its official URL in the server’s CapabilityStatement.rest.resource.supportedProfile element.

The NHS England Profile’s official or “canonical” URL can be found on each NHS England Profile page.

### Profile Support & Interaction Support

Systems **MAY** deploy, and support, one or more NHS England Profiles to represent clinical information and the NHS England interactions to access the information. Systems that implement both can claim conformance to the NHS England Profile content structure and the RESTful or messaging interactions defined for it. This is done by implementing all, or parts of, the NHS England CapabilityStatement into their capabilities.

To claim conformance to a NHS England Profile a server:

- **SHALL** be able to populate all Profile data elements that are mandatory and/or flagged as "Must Support" as defined by that Profile’s StructureDefinition.
- **SHALL** declare conformance with the NHS England Capability Statement by including its official URL in the server’s CapabilityStatement.instantiates element.
- **SHALL** specify the full capability details from NHS England CapabilityStatement it claims to implement.
- Declare support for the NHS England Profile by including its official URL in the server’s CapabilityStatement.rest.resource.supportedProfile element.
- Declare support for the NHS England Profile’s FHIR RESTful transactions or messaging interactions.

The NHS England Profile’s official or “canonical” URL can be found on each Profile page.

This is the conformance that all NHS England programs SHALL conform to going forward.


