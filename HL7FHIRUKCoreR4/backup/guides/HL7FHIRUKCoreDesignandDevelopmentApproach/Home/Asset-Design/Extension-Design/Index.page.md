---
topic: extension-design
---
# {{page-title}}

It is common for specific implementations to have valid requirements that are not part of the agreed common requirements modelled in the FHIR standard. Incorporating all specific use cases would make the standard too cumbersome. Therefore, additional valid requirements can be implemented as extensions to the agreed common resources. Further information about <a href="https://www.hl7.org/fhir/r4/extensibility.html">extensibility</a> is available.

There are two basic types of extensions used by UK Core:

- **Simple extensions**: A simple extension has a single <code>Extension.url</code>element and a single <code>Extension.value\[x\]</code> element, which may have many datatypes associated with it. See <a href="https://www.hl7.org/fhir/r4/extensibility.html#Extension">Extension Element</a> for more details. 
- **Complex extensions**: A complex extension has a single <code>Extension.url</code>element and a single <code>Extension.extension</code> element. The latter contains a nested structure and are used for one of two reason:
  - The extension has complex content, which is presented as a nested tree of values and defined locally within the extension.
  - The extension is extended with an additional extension defined separately.

Currently the UK Core does not use modifierExtensions, so no guidance is given here on this type. 
More information on <a href="http://hl7.org/fhir/r4/extensibility.html#modifierExtension">modifierExtensions</a> is available in the FHIR specification.

Each Extension SHALL have an associated example to describe its usage, and the example SHALL be added to the example tab within the relevant profile and the extension page. 

Any binding in an Extension SHALL only be done to CodeableConcept value's - cvode and coding values SHALL NOT be used.

Referencing to resources SHOULD be to the base resource rather than a UK Core Profile, unless agreed.
 
---
