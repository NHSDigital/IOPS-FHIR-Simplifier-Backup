## {{page-title}}

The Send Document capability provides a simple and standardised means of sending a document, such as a PDF, an image, or HTML file to a GP practice system. Each message sent using the Send Document capability makes use of the GP Connect Messaging components, MESH, and ITK3 to deliver the message.

All messages sent using this capability will be FHIR® Messages, defined as a FHIR composition, constructed to meet the ITK3 standard and have a specific payload structure.

{{render: gpc-send-doc-overview.png}}

GP Connect aims to support better clinical care by opening up information and data held within GP principal clinical systems for use across health and social care. The GP Connect vision will be achieved by standardising integration and simplifying the operating model. Find out more on the [NHS Digital GP Connect homepage](https://digital.nhs.uk/services/gp-connect).

GP Connect has initially focused on delivering HTTP FHIR® APIs. The current GP Connect FHIR API specification is found at https://digital.nhs.uk/services/gp-connect/. An additional set of capabilities, under the badge GP Connect Messaging, is described in this specification. These new capabilities are focused on enabling updates to GP practice systems.

---