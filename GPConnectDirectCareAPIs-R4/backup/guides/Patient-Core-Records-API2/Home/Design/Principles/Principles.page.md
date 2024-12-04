### Architecture principles

The API would conform to the following NHS England Architecture principles:

__Deliver Sustainable Services__

A single API would enable the use of efficient interactions where a solution would meet many different requirements with regards to data transfer. It would also be scalable to accept increasing demand. 

Adopting latest protocol ensures efficient and quick data movement minimising the need to store data in additional repositories.

__Internet First__

RESTful interactions would utilise the HTTP protocol and can support multiple data formats.
Use open standards to ensure the API can integrate easily with other systems, reducing redundancy.
Promote reuse of existing APIs to avoid duplicating efforts.

__Adopt appropriate cyber security standards__

Integrating the API Management platform would ensure appropriate security measures are in place for data transfer

__Use Platforms__

Digital services should adopt open data and technology standards.
Would be integrated into the APIM platform giving access to other central services. Also, would conform to the FHIR UK Core standard.

__Interoperability with open data and technology standards__

UK Core specification adheres to the HL7 R4 FHIR standard, positioning it as the benchmark for any forthcoming developments under the FHIR standard. The standard is accessible and allows new innovators to collaborate and create solutions using the standard.


### API Principles

The API would also follow the NHS England API principles.

__Make learning easier__

Our API documentation will be online, accessible and clear. We will provide hands-on tutorials and sandboxes so you can try things out. We will provide feedback channels so you can tell us what you think.

__Make designing and building easier__

Our APIs will be internet-facing and simple to use. We will use modern open standards, such as REST, FHIR, OAuth 2.0. We will use clinical information standards such as SNOMED CT, dm+d, ICD, OPCS and UTL. We will use NHS Care Identity Service 2 (NHS CIS2) and NHS login for authentication.

__Make testing easier__

Our test environments will be self-service and well-documented. We will provide easy-to-use sandboxes for early developer testing.

__Make onboarding easier__

Our API onboarding process will be as simple as possible, only asking you to do things that are needed. We won't compromise clinical safety, privacy or security. 

__Make help and support easier__

Our API platform will be as self-service as possible. When you do need help, we will provide simple and reliable support.


#### Other principles that the API adheres to:

- The GP clinical record is not the complete patient record

- In the event of a record being updated, other interested systems would need to be notified

-  A system should be able to share parts of the patient record using the API

- Any system onboarded to use the API should be able to accept updates to a record (where possible)



