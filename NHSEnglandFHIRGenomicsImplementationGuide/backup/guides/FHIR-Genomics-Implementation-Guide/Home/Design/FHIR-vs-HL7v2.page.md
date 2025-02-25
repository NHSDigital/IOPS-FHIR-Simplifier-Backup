## {{page-title}}

It is well known that HL7v2 is ubiquitous for order comms within Pathology, and the Diagnostics domain more generally. However, there are a number of limitations with the HL7v2 approach which necessitates the move to FHIR within Genomic Order Management. 

A general comparison between HL7v2 and FHIR is given on the [FHIR HL7v2 page](https://www.hl7.org/fhir/R4/comparison-v2.html) but specifically for Genomics, there are a few requirements within order management which could not be fulfilled using a standard HL7v2 interface:

* The first major issue is HL7v2 only supports the messaging paradigm, this means with each message a full payload of information needs to be included, as the message itself is a single entity. This is resolved within FHIR through the use of the RESTful paradigm, where entities within a test order have been split into separate resources which can be manipulated independently (e.g. created, updated and deleted). This allows much more flexibility within the ordering process and allows ordering entities to update an order within additional clinical information without a new request needing to be generated.

* A consequence of the messaging paradigm is that, by default, only point-to-point messages are supported, e.g. from requester to fulfiller. This does not meet the needs of Genomic Order Management, where national visibility of orders (for both requesters to see the status of their orders, and the national back office to have a real-time view of throughput), and distributed fulfilment (i.e. multiple organisations responsible of different stages in the processing of a test order) were core requirements. FHIR supports these requirements through use of the FHIR Workflow Broker pattern, which provides a central service for viewing orders, as well as more flexibility in defining Tasks required to fulfil those orders.

* The OML/ORU HL7v2 message structure typically only allows for a single request and response (result). Within Genomic Order Management, there is the requirement for more granular status updates throughout the fulfilment of an order, as the process involves multiple, possibly parallel, steps and organisations (as detailed within the NGTP). This is implemented within FHIR as a set of Tasks, each potentially assigned to a different organisation, allowing independent status updates, with a set of statuses and businessStatuses to capture all possible states outlined within the NGTP, including on-hold and failure states.

* Genomic test orders require a large dataset, covering the clinical history of the proband and related family members, which do not fit within the standard HL7v2 OML message structure. FHIR transactions allow for rich flexibility in referencing resources whilst still conforming to a predefined schema, detailed within GraphDefinitions. 

* HL7v2 in general does not cater for extensions in a structured manner. Z segments can be defined for data not typically contained within a particular message, but a central location where these Z segments can be defined and commonly understood does not exist. FHIR makes use of a well structured and defined Extensibility framework, allowing elements not in the base resources to be defined within the appropriate resource and at the appropriate level, explicitly calling out the use context for the extension and restricting codes used where required.

* Finally, HL7v2 does not have cross version consistency, or even cross implementation consistency, with segments not being supported or not existing altogether, within different versions and implementations of the same trigger event. For this reason, a central FHIR implementation guide has been developed to concretely outline the capabilities required of connecting systems. 

A number of alternatives/transformation mechanisms are being investigated by the central NHS England Genomics Unit to help uplift HL7v2 systems, or allow limited connectivity with the central broker, as detailed below. Thouo native FHIR integration is still preferred:

* Maps from HL7v2 OML_O21 to FHIR for the initial order message. While these have not been explicitly defined within StructureMaps (due to inter-version inconsistencies in HL7v2 only limited benefits would be obtained from these), the tables should allow users to create transformations within their local systems, uplifting data from v2 into the appropriate FHIR resources. It is expected that any data items not supported by the local HL7v2 interface will need to be captured as OBX segments. 

* Status updates through specifically coded OBX segments, using the HL7v2 resulting mechanism (to be confirmed).

* Support for draft requests within the central broker, allowing partial information to be uploaded from a HL7v2 based system, with further enrichment via another interface, e.g. web portal, before submission of a complete order (to be confirmed). 

* Development of the Genomic Order Management Web Portal, to present data not mappable to a HL7v2 message.

For a more general introduction to the benefits of using FHIR, please see the FHIR overview pages, including those for [General Users](https://www.hl7.org/fhir/R4/overview.html), [Developers](https://www.hl7.org/fhir/R4/overview-dev.html), [Clinicians](https://www.hl7.org/fhir/R4/overview-clinical.html) and [Architects](https://www.hl7.org/fhir/R4/overview-arch.html).