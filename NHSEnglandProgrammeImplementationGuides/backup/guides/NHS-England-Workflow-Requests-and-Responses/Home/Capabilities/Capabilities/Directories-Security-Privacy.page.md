## {{page-title}}

### Audit

| Name | Description | Other Standards |
|--
| [IHE Basic Audit Log Patterns (BALP)](https://profiles.ihe.net/ITI/BALP/) | The Basic Audit Log Patterns (BALP) Implementation Guide is a Content Profile that defines some basic and reusable AuditEvent patterns. This includes basic audit log profiles for FHIR RESTful operations to be used when there is not a more specific audit event defined. A focus is on enabling Privacy centric AuditEvent logs that hold well-formed indication of the Patient when they are the subject of the activity being recorded in the log. Where a more specific audit event can be defined, it should be derived off of these basic patterns. | [IHE Audit Trail and Node Authentication (ATNA)](https://profiles.ihe.net/ITI/TF/Volume1/ch-9.html) |
| [IHE Add RESTful ATNA (Query and Feed)](https://www.ihe.net/uploadedFiles/Documents/ITI/IHE_ITI_Suppl_RESTful-ATNA.pdf) | This supplement extends the functionalities of the ATNA Profile by introducing RESTful operations that could be used to submit and retrieve audit records. This allows light weight applications to easily manage the creation and the access audit information. This supplement is based on FHIR protocol and uses FHIR AuditEvent Resources in order to exchange audit records content. This supplement also defines a query transaction that enables access to raw syslog messages. | [IHE Audit Trail and Node Authentication (ATNA)](https://profiles.ihe.net/ITI/TF/Volume1/ch-9.html) |

### Security and Application Launch

| Name | Description |
|--
| [SMART App Launch](https://www.hl7.org/fhir/smart-app-launch/) | This implementation guide describes a set of foundational patterns based on OAuth 2.0 for client applications to authorize, authenticate, and integrate with FHIR-based data systems. The patterns defined in this specification are introduced in the sections below. For background on SMART Health IT, see smarthealthit.org. |
| [IHE Internet User Authorization (IUA)](https://profiles.ihe.net/ITI/IUA/index.html) | This profile is motivated by customer requirements for authorizing network transactions when using HTTP RESTful transports. IHE has authorization profiles for the Web Services and SOAP based transactions, and this profile provides an authorization profile for the HTTP RESTful transactions. |

### Care Directory Services

| Name | Description | Other Standards |
|--
| [IHE Mobile Care Services Discovery (mCSD)](https://profiles.ihe.net/ITI/mCSD/index.html) | The Mobile Care Services Discovery (mCSD) Profile supports RESTful queries across related care services resources. The loosely coupled design and flexible querying capability of the mCSD Profile means it can be deployed within a variety of eHealth architectures and support a wide array of care workflows. | [INTEROPen and NHS England Care Connect API](https://nhsconnect.github.io/CareConnectAPI/) |