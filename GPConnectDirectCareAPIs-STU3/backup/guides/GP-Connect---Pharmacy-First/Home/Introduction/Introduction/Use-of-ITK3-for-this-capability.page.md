## {{page-title}}

Due to timeline constraints, a decision was made to pivot to using ITK3/MESH as the delivery mechanism, with the [GP Connect data model](https://simplifier.net/guide/gpconnect-data-model/Home?version=current) to be used in the payload. 

This capability is only authorized for Pharmacy First. The intention is to focus on the ingestion of STU3 Care Connect profiles using ITK3 for pharmacy, and then swap out the delivery mechanism for a full API at a later date. The full API will still use the STU3 representation of the GP Connect data model, only the delivery mechanism will change.

The GP Connect data model, which is a STU3 representation, has been chosen for this capability to align to [Access Record: Structured](https://digital.nhs.uk/developer/api-catalogue/gp-connect-access-record-structured-fhir#top). Suppliers have already developed against this specification, so it will be quicker to ingest the data from these profiles. The strategic goal is to create a RESTful GP Connect API for both accessing and updating the patient GP record within FHIR R4 (UK Core), harnessing the GP Connect data model, promoting usage of services such as the National Record Locator and the National Event Manager where possible.

---