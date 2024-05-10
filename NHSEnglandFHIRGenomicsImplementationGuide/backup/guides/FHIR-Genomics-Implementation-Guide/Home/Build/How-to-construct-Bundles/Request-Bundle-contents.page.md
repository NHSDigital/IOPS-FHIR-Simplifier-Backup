## {{page-title}}

## Genetic Testing Request
The genetic testing information is exchanged using FHIR Transaction Bundle. This section shows the Bundle structure and the relationship between the resources which make up the Bundle.

The Bundle uses the following resource to carry the related business entity information:

**Test Request Summary** - This business entity is used to capture details of the test and supporting information from the requestor and uses the ServiceRequest FHIR resource.

The data items and resources used in the Request Bundle are mapped from the Genomics Minimum Dataset ({{pagelink:Home/Design/Clinicalheadings}})

The following diagram identifies key fhir resources included within a Genetic Testing Request bundle, and how these resources are related.

{{render:diagrams-gms-test-request-logical-model-v2}}
