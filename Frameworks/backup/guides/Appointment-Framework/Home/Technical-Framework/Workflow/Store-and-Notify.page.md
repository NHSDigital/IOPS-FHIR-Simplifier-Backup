## {{page-title}}

See also [NHS England Interoperability Handbook - Store and Notify](https://www.england.nhs.uk/wp-content/uploads/2017/03/interoperabilty-handbk.pdf)


Store and Notify is principally a modernistion of the {{pagelink:Home/Technical-Framework/Workflow/HL7-FHIR-Message-and-Documents--HL7-v3-and-CDA.page.md}}. 
This changes the pattern from **sending** the Document/Message to **sharing** the Document/Message. This relies on {{pagelink:Home/Technical-Framework/Shared-Clinical-Documents}} being implemented.

{{render:diagrams-TechnicalFramework-Workflow-DocumentNotificaton}}

In both cases an event notification is sent to the consumer, who can retrieve the data if required. 

This also applies to {{pagelink:Home/Technical-Framework/Workflow/HL7-v2-Events-and-Ad-Hoc-FHIR-RESTful-Events.page.md}} with the clinical data being shared using 
{{pagelink:Home/Technical-Framework/Query-API}} and/or 
{{pagelink:Home/Technical-Framework/Shared-Clinical-Documents}}

{{render:diagrams-TechnicalFramework-Workflow-EventNotification}}

