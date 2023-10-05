## {{page-title}}

Use of attachments, either in test orders or referenced in diagnostic reports is still under discussion. 

There are a number of elements, such as PDF test reports and RoD documents which the national strategy indicates should not be stored on a national service, but instead should be accessible directly from the originating/data controller system. For the alpha and beta phase, where  suppliers would struggle to meet timescales, the documents will be stored in the national service to simplify integration, but with a clear roadmap for changing where the documents and data are stored and retrieved. This could use a service such as NRL, possibly proxied through the national service to remove the risk of consumers losing access to the data and to decouple the development and migration of providers from a central document store to distributed document storage and retrieval.

This section will be updated as requirements are elicited.

Examples of attachments which may be used are:

- PDF copies of patient history and diagnostic reports
- DICOM or other images included as part of the patient history
- Variants of Unknown Significance (VUS) files which may be attached to genomic reports

It is expected PDFs in messages will be sent within the body of the FHIR message as a base64 encoded string.

Images and VUS files may be quite large in size so a separate image/variant store may need to be used to host this data centrally. Alternatively, suppliers can ensure this data can be queried and retrieved by the Genomic Medicine Service, either via NRL or externally queryable APIs, allowing these attachments to be referenced by their URL as per {{pagelink:Bundle-referencing}}.
