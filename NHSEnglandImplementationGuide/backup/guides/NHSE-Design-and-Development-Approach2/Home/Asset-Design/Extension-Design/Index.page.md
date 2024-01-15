---
topic: extension-design
---
# {{page-title}}

Occasionally there will be requirements within an NHS England programme which are England specific or has a specific use-case. Therefore, additional valid requirements can be implemented as Extensions to existing UK Core or NHS England IG resources. Further information about extensibility is available.

There are two basic types of extensions within NHS England IG:

- **Simple extensions**: A simple extension has a single <code>Extension.url</code>element and a single <code>Extension.value\[x\]</code> element, which may have many datatypes associated with it. See <a href="https://www.hl7.org/fhir/r4/extensibility.html#Extension">Extension Element</a> for more details. 
- **Complex extensions**: A complex extension has a single <code>Extension.url</code>element and a single <code>Extension.extension</code> element. The latter contains a nested structure and are used for one of two reason:
  - The extension has complex content, which is presented as a nested tree of values and defined locally within the extension.
  - The extension is extended with an additional extension defined separately.

Currently the NHSE IG does not use modifierExtensions, so no guidance is given here on this type. 
More information on <a href="http://hl7.org/fhir/r4/extensibility.html#modifierExtension">modifierExtensions</a> is available in the FHIR specification.

---