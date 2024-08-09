## {{page-title}}

{{page:Home/Design/Profile-Design/Metadata-Usage.page.md}}

<br><br>

### The Extension Root Element

Extensions are optional within the UK Core (minimum cardinality of 0), but certain use cases may mandate their use. Currently, all UK Core extensions are modelled as being optional at the extension root element. Where the use case requires an extension to be mandated, the Implementation Guide for that use case will specify the requirements.

### Extension Bindings When the Value is a Coded type
If any of the <code>extension.value</code> elements is constrained to a coded type e.g. one of Code, Coding, or CodeableConcept, the <code>extension.value</code> SHALL be bound to a ValueSet.

Further information about <a href="https://www.hl7.org/fhir/r4/datatypes.html">FHIR datatypes</a> is available.

### Cardinality of a value[x] element
**Simple extension** - The UK Core mandates the use of <code>Extension.value[x]</code> for a simple extension, that is, a cardinality of 1..1.

**Complex extension** - The UK Core mandates the use of <code>Extension.extension:<i>[Element]</i>.value[x]</code> for a complex extension, that is, a cardinality of 1..1.


---
