## {{page-title}}

The API itself is a simple REST-based API which harnesses FHIR in the request and response body.
The reasons for this design approach is to create a FHIR-version agnostic API that supports the transfer of healthcare data using an agreed standard (usually FHIR) between NHS IT systems.

FHIR (Fast Healthcare Interoperability Resources) is a global standard for health care data exchange. It is the successor to the HL7 V3 standard.

FHIR:

- defines specific resources for the health care domain, such as ==Patient== and ==Observation==, and also defines common data items for those resources
- can be adapted for local requirements using profiles, extensions, terminologies and more
- defines rules for how to access resources via RESTful APIs
- can also be used for messaging and document solutions


### GET

This interaction is used to request data from an endpoint. This could be to a system or a repository as long as it has the API to respond appropriately.

The patient clinical record holds many types of data and it is essential that different parts of the record is accessible and are aceessed in a consistent manner. The request and any responses would be in the represented using the FHIR standard.


### POST

The POST interaction will be used to send data to an endpoint. This will usually be a creation or an update of a record.

See the {{pagelink:Home/API/Endpoints.page.md}} page for the FHIR resources used to request and update the record.

