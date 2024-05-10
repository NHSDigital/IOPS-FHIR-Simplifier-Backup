## {{page-title}}

Resources in Bundles SHOULD NOT use contained resources. 

References to other resources in the Bundle SHOULD use the fullUrl uuid, e.g. 

```
"reference": "urn:uuid:66c519dd-423f-4238-89c8-91c5be52f330"
```

References to other resources not included in the Bundle SHOULD use the path for the resource, including the uuid, if this can be found on the GMS central broker e.g. 

```
"reference": "Specimen/840d075e-0480-4134-ae51-27f572731cc8"
```

If the resource is hosted on another NHS service, for example patient records on PDS, these should be referenced by identifier using the appropriate system for the identifier e.g. 

```
"reference": {
  "identifier": {
    "system": "https://fhir.nhs.uk/Id/nhs-number",
    "value": "9999999999"
  }
}
```

If a resource is contained on another system, outside NHS central services, this SHOULD be referenced with an absolute url. The URL SHALL be resolvable and preferably return a FHIR resource of the appropriate type e.g.

```
"reference": "https://www.christie.nhs.uk/ehr/LabOrder123456"
```

All profiles within transaction bundles should reference each other i.e. none should be orphaned.

Any additional resources not linked from another resource in a transaction bundle SHALL be excluded, or sent in a separate transaction. The expected list of resources and cardinalities in a typical test order or report transaction are detailed in {{pagelink:Home/FHIRAssets/MessageDefinitions}}.

## Resource Reference (Duo/Trio Tests)
When the test type is Duo or Trio there will usually be specimens from more than one patient. Due to the way references work within FHIR, the Task resource will reference the Specimen resources for all participants within the “input” element, and each specimen will reference the patient it relates to using the “subject” element.

{{render:diagrams-duo-specimen}}