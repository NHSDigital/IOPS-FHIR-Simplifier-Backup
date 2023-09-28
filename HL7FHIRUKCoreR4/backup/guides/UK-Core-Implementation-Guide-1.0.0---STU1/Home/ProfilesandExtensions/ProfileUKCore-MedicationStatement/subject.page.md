## `subject`

A reference to the patient.

Within a FHIR Messaging or FHIR Document implementation, include a {{pagelink:Profile-Patient-fa365b29-79b9-4024-9b49-729ac15e401c}} resource within the Bundle with at least the minimum dataset populated as defined within the UK Core standard. The `reference` points to the resource in the Bundle.

Within a RESTful implementation a `reference` and/or `identifier` SHALL be provided that allows the consumer system to query another API if they need to access the complete {{pagelink:Profile-Patient-fa365b29-79b9-4024-9b49-729ac15e401c}} resource. 

For implementations within England and Wales, the `identifier` could be the patient's **NHS Number**, allowing a consumer system to use the NHS Digital Personal Demographics Service FHIR API to return a Patient resource.

For implementations within Scotland, the `identifier` could be the patient's **CHI Number**.

---