## {{page-title}}

In contrast to the synchronous FHIR® API approach, which has been taken to enable read-only access to patient information, updates to patient data will be fulfilled through a messaging approach.

Update messages will:

- be sent using [MESH](https://digital.nhs.uk/services/message-exchange-for-social-care-and-health-mesh)
- use the [HL7 FHIR® STU3](http://hl7.org/fhir/stu3/index.html) interoperability standard to define their structure
- include FHIR® messaging information as defined by the [ITK3 Message Distribution standard, v2.10.0](https://developer.nhs.uk/apis/itk3messagedistribution-2-10-0/) standard

---