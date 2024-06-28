## {{page-title}}

All messages sent according to the ITK3 standard specification are constructed using the HL7 FHIR® STU3 standard using the FHIR Messaging framework.

The ITK3 standard builds on the FHIR Messaging framework through a set of messaging extensions, which are provided through a profile of FHIR MessageHeader resource.

This extension of the FHIR messaging framework provides some messaging options such as:

- the ability for a sender to request a positive or negative “infrastructure” acknowledgement message to be returned which indicates the success or failure of the processing of the message at a technical level
- the ability for a sender to request a positive or negative “business” acknowledgement message to be returned which indicates the success or failure of the processing of the message at a business process level
- various message meta-data elements

Please refer to the messaging capability and messaging use case pages for details of which of these options is mandated or recommended for the particular message being created.

---