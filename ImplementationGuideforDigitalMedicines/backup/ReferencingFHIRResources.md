# {{page-title}}

The method by which other FHIR resources, e.g. `Medication` or `Patient`, are referenced within a FHIR resource will be a local implementation decision.

There are three options;

1. Referenced by URL to a FHIR Server
2. Referenced by an identifier to a resource within the same FHIR Bundle
3. Referenced by an identifier to a “contained” resource within the resource

FHIR snippets using XML notation are as follows:

---