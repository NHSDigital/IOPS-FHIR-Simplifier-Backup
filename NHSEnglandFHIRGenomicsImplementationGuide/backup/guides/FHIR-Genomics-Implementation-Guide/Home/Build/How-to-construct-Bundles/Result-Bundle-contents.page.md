## {{page-title}}

## Genetic Testing Response
The genetic testing response information is exchanged using FHIR Transaction Bundle. This section shows the example Bundle structure and the relationship between the resources which make up the Bundle.

The Bundle uses the following resource to carry the related business entity information:

**Test Request Response** - This business entity is used to capture details of the genetic testing response and uses the DiagnosticReport FHIR resource.

The data items and resources used in the Response Bundle are mapped from the [Genomics Reporting IG](http://hl7.org/fhir/uv/genomics-reporting/index.html), published by the HL7 Clinical Genomics Working Group. This model is still under review for use in the UK.

Alignment of this model to the [EU Laboratory Report Guidance](https://build.fhir.org/ig/hl7-eu/laboratory/), e.g. representation of test reports as DiagnosticReports or Documents within Genomic Order Management, is still pending.
 
The following diagram identifies key fhir resources included within a National Diagnostics - Genetic Testing Response bundle, and how these resources are related.

{{render:diagrams-gms-report-response-logical-model-v2}}