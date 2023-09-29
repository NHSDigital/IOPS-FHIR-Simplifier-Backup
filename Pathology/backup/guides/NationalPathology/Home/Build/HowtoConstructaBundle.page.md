---
topic: HowtoConstructaBundle
---
### How to Construct a FHIR Bundle

The Pathology information is exchanged using FHIR Bundles. This section shows the Bundle structure and the relationship between the resources which make up the Bundle. 

The Bundle uses the following resource to carry the related business entity information:
- **Test Request Summary** - This business entity is used to capture details from the requestor and uses the {{pagelink:ServiceRequest}} FHIR resource.
- **Test Report** - This business entity is used to capture details regarding all the tests performed by the performing organisation and uses the {{pagelink:DiagnosticReport}} FHIR resource.
- **Specimen** - This business entity is used to capture specimen (sample) details and uses the {{pagelink:Specimen}} FHIR resource.
- **Test Group** - This business entity is used to capture groups of test results. These can be a battery of tests or a single test, or a combination of all of these entities. It uses the {{pagelink:Observation}} FHIR resource.
- **Test Result** - This business entity is used to capture details for a single test result and uses the {{pagelink:Observation}}.

Each of these business entities is mapped to FHIR in the data mapping pages.

## Bundle Diagram ##

The following diagram provides a visual indication to assist implementers with understanding which resources are included within a National Pathology bundle, and how these resources are related. 


{{render:Bundle-diagram}}