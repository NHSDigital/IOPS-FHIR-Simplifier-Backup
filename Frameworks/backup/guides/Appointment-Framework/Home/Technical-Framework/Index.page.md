## {{page-title}}

<div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-information"></i><b> Important:</b> The content on these pages have not been approved or adopted by NHS England.</div>

### People, Process and Technology

{{render:diagrams-CareProcess-ppt}}

This approach is aligned to [UK Government Design Principles](https://www.gov.uk/guidance/government-design-principles) in particular.

- Technical Frameworks are based on existing common patterns in use in health and care (**Design with data**) which support clinical pathways and processes (Start with user needs) which spread over several care settings (**Understand context**)
- Existing services (**Design with data**) may indicate a mix of interoperability standards (solutions/frameworks may not be HL7 FHIR based)
- Care Coordination will take a pragmatic approach to the data model, this is likely to lead to a simple data model (**Do less**)
- We need to be open to health and care providers issues, and provide support, we should not be hiding our support (**Do the hard work to make it simple and Make things open: it makes things better**)
- This will not be delivered in one go and may take time (**Iterate. Then iterate again**)
- We aim to improve consistency, not standards **Be consistent, not uniform** 


### Principles

- Data is shared as default, data is not sent. This allows all people involved in a patients care to view records, sending is typically between one or two providers.
- Pragmatic. Frameworks will focus on practicality, it will not focus solely of data standards which have often been complex.
- Generic and Pathway focused. Frameworks will align to common requirements or issues on multiple pathways. 
- Open and Collaborative. 
- Start Small and Evolve.  

### Evolve

{{render:diagrams-CareProcess-elaboration}}

### IHE Technical Framework Map

- [IT Infrastructure (ITI) Technical Framework Volume 1](https://profiles.ihe.net/ITI/TF/Volume1/index.html)
- [IHE IT Infrastructure Technical Framework Volume 2](https://profiles.ihe.net/ITI/TF/Volume2/index.html)

Selected ITI interactions:

| IHE ITI Volume 1 <br/> Use Case | IHE ITI Volume 2 <br/> Technical Framework| NHS England Technical Framework | 
|--
| [Cross-Enterprise Document Sharing (XDS.b)](https://profiles.ihe.net/ITI/TF/Volume1/ch-10.html) <br/> [Mobile Health Document Sharing (MHDS)](https://profiles.ihe.net/ITI/MHDS/index.html) | Registry Stored Query [ITI-18] <br/> Retrieve Document Set [ITI-43] | {{pagelink:Home/Technical-Framework/Shared-Clinical-Documents}} Get Document List |
| [Patient Administration Management (PAM)](https://profiles.ihe.net/ITI/TF/Volume1/ch-14.html) | Patient Identity Management [ITI-30] | {{pagelink:Home/Technical-Framework/Workflow/HL7-v2-Events-and-Ad-Hoc-FHIR-RESTful-Events.page.md}} | 
| [Patient Administration Management (PAM)](https://profiles.ihe.net/ITI/TF/Volume1/ch-14.html) | Patient Encounter Management [ITI-31] | {{pagelink:Home/Technical-Framework/Workflow/HL7-v2-Events-and-Ad-Hoc-FHIR-RESTful-Events.page.md}} | 
| [Retrieve Form for Data Capture (RFD)](https://profiles.ihe.net/ITI/TF/Volume1/ch-17.html)| Retrieve Form [ITI-34] |  {{pagelink:Home/Technical-Framework/Structured-Data-Capture}} | 
| [Retrieve Form for Data Capture (RFD)](https://profiles.ihe.net/ITI/TF/Volume1/ch-17.html) | Submit Form [ITI-35] |  {{pagelink:Home/Technical-Framework/Structured-Data-Capture}} |
| [ Cross-Community Access (XCA)](https://profiles.ihe.net/ITI/TF/Volume1/ch-18.html)| Cross Gateway Query [ITI-38] | {{pagelink:Home/Technical-Framework/Shared-Clinical-Documents/Federated-Document-API.page.md}} |  
| [Cross-Enterprise Document Sharing (XDS.b)](https://profiles.ihe.net/ITI/TF/Volume1/ch-10.html)  <br/> [Mobile Health Document Sharing (MHDS)](https://profiles.ihe.net/ITI/MHDS/index.html) | Provide and Register Document Set-b [ITI-41] <br/> Simplified Publish [ITI-105]  <br/> Provide Document Bundle [ITI-65]| {{pagelink:Home/Technical-Framework/Shared-Clinical-Documents}} Put Document |
| [Cross-Enterprise Document Sharing (XDS.b)](https://profiles.ihe.net/ITI/TF/Volume1/ch-10.html)  <br/> [Mobile Health Document Sharing (MHDS)](https://profiles.ihe.net/ITI/MHDS/index.html)| Register Document Set-b [ITI-42]|  {{pagelink:Home/Technical-Framework/Shared-Clinical-Documents}} Register Document|
| [Cross-Enterprise Document Sharing (XDS.b)](https://profiles.ihe.net/ITI/TF/Volume1/ch-10.html)  <br/> [Mobile Health Document Sharing (MHDS)](https://profiles.ihe.net/ITI/MHDS/index.html) | Retrieve Document Set [ITI-43] <br/> Retrieve Document [ITI-68] |  {{pagelink:Home/Technical-Framework/Shared-Clinical-Documents}} Get Document | 
| [Patient Administration Management (PAM)](https://profiles.ihe.net/ITI/TF/Volume1/ch-14.html) | Patient Identity Feed HL7 V3 [ITI-44] <br/> Patient Identity Feed FHIR [ITI-104] | {{pagelink:Home/Technical-Framework/Health-Administration/Patient-Identifier-Cross-Reference.page.md}} | 
| [Patient Demographics Query (PDQ)](https://profiles.ihe.net/ITI/TF/Volume1/ch-8.html#8) | Patient Demographics Query [ITI-21] <br/> Patient Demographics Query HL7 V3 [ITI-47] <br/> Mobile Patient Demographics Query [ITI-78] | {{pagelink:Home/Technical-Framework/Health-Administration/Patient-Demographic-Queries.page.md}} |
| [Sharing of IPS (sIPS)](https://profiles.ihe.net/ITI/sIPS/index.html) |  | {{pagelink:Home/Technical-Framework/Shared-Clinical-Documents/Clinical-Document-Architecture--FHIR-Documents.page.md}} |
| [Cross-Enterprise Document Workflow Content Profile (XDW)](https://profiles.ihe.net/ITI/TF/Volume1/ch-30.html) | | {{pagelink:Home/Technical-Framework/Workflow/FHIR-Workflow.page.md}} <br/> (note this is primarily resource focused) |

