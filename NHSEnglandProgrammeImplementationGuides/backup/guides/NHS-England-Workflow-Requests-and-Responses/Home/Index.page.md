# {{page-title}} 

This is intital elaboration of a EPR foundation interoperability specification which will serve as a basis for subsequent standards.

This guide may include NHS England Supplements to IHE or HL7 standards.

## Use Cases

- [Cross Organisational Workflow (workflow and tasks)](https://nhsd-confluence.digital.nhs.uk/pages/viewpage.action?pageId=836678052)
- [Shared Assessments (health checks and workflow)](https://nhsd-confluence.digital.nhs.uk/pages/viewpage.action?pageId=836678071)
- [NHS England National Proxy Service](https://nhsd-confluence.digital.nhs.uk/pages/viewpage.action?pageId=778783403)

## NHS England Frameworks

| Producer | Consumer | Name | Description |
|--
| &#10003; | &#10003; | **Basic Tasking** | is based on [FHIR Workflow](https://hl7.org/fhir/R4/workflow-module.html) and aims at improving care coordination along a patient pathway. |
| &#10003; |  | **Patient Encounter Notification** | Is a HL7 FHIR based method for notifying other providers (and applications) of key health administrative events along a pathway. It is compatible with HL7 v2 ADT, [IHE Patient Administration Managment](https://profiles.ihe.net/ITI/TF/Volume1/ch-14.html) and (NHS England) HSCIC ITK - HL7v2 Interoperability Message Specifications. This is not intended to replace HL7 v2 usage within a secondary care organisation but rather extend this notification to other sectors, i.e. a HL7 v2 ADT/IHE PEM can be easily transformed into a HL7 FHIR Patient Encounter Notification. |

## International Frameworks

### Shared Records

The following are recommended to be be used in conjunction with this specification.

| Producer | Consumer | Name | Description |
|--
| &#10003; |  | [HL7 International Patient Access (IPA)](https://build.fhir.org/ig/HL7/fhir-ipa/)  or [IHE Query for Existing Data for Mobile (QEDm)](https://build.fhir.org/ig/IHE/QEDm/branches/master/index.html) | This specification describes how an application acting on behalf of a patient can access information about the patient from a clinical records system using a FHIR R4 based API. The clinical records system may be supporting a clinical care provider (e.g., a hospital or a general practitioner), a health data exchange, or other system managing patient records, including a national health record system. |
| &#10003; |  | [IHE Mobile access to Health Documents (MHD)](https://profiles.ihe.net/ITI/MHD/index.html) | The Mobile access to Health Documents (MHD) Profile defines one standardized interface to health document sharing (a.k.a. an Application Programming Interface (API)) for use by mobile devices so that deployment of mobile applications is more consistent and reusable. In this context, mobile devices include tablets, smart-phones, and embedded devices including home-health devices. This profile is also applicable to more capable systems where needs are simple, such as pulling the latest summary for display. The critical aspects of the “mobile device” are that it is resource-constrained, has a simple programming environment (e.g., JSON, JavaScript), simple protocol stack (e.g., HTTP), and simple display functionality (e.g., HTML browser). The goal is, in part, to avoid burdening the client with additional libraries such as those that are necessary to process SOAP, WSSE, MIME-Multipart, MTOM/XOP, ebRIM, and multi-depth XML. |
| &#10003; |  | [IHE Patient Demographics Query for Mobile (PDQm)](https://profiles.ihe.net/ITI/PDQm/) | The Patient Demographics Query for Mobile (PDQm) Profile defines a lightweight RESTful interface to a patient demographics supplier leveraging technologies readily available to mobile applications and lightweight browser based applications. |

### Structured Data Capture

| Producer | Consumer | Name | Description |
|--
| &#10003; |  | [HL7 Structured Data Capture](https://build.fhir.org/ig/HL7/sdc/) | Paper forms exist all over healthcare. They get filled out by patients, relatives, administrators, clinicians - essentially everyone. The FHIR standard defines some basic ways share forms (empty ones and completed ones), however it only supports the capabilities that almost all forms need to have. This implementation guide defines additional capabilities, including the ability to automatically fill in some of the form answers with information that might already have been entered somewhere else, the ability to automatically calculate certain fields like age, the ability to better control what a form looks like, etc. It defines a wide variety of 'features' covering different aspects of forms (how forms look, how they behave, what types of systems can use forms and what they can do with them, etc.) The intent is to help ensure that different types of systems that implement the same 'feature' do so in the same way. |

### Event Notifications

The following are recommended to be used in conjunction with this specification.

| Producer | Consumer | Name | Description |
|--
| &#10003; |  | [IHE Patient Identifier Cross-referencing for mobile (PIXm)](https://profiles.ihe.net/ITI/PIXm/index.html) | The Patient Identifier Cross-reference for Mobile (PIXm) Profile provides RESTful transactions for mobile and lightweight browser-based applications to create, update and delete patient records in a Patient Identifier Cross-reference Manager and to query the Patient Identifier Cross-reference Manager for a patient’s cross-domain identifiers. |
|  |  &#10003; | [IHE Patient Master Identity Registry (PMIR)](https://profiles.ihe.net/ITI/PMIR/) | The Patient Master Identity Registry (PMIR) Profile supports the creating, updating and deprecating of patient master identity information about a subject of care, as well as subscribing to changes to the patient master identity, using the HL7 FHIR standard resources and RESTful transactions. In PMIR, “patient identity” information includes all information found in the FHIR Patient Resource such as identifier, name, phone, gender, birth date, address, marital status, photo, others to contact, preference for language, general practitioner, and links to other instances of identities. The “patient master identity” is the dominant patient identity managed centrally among many participating organizations (a.k.a., “Golden Patient Identity”). |
| &#10003; ITI-111 only | &#10003; | [IHE Document Subscription for Mobile (DSUBm)](https://profiles.ihe.net/ITI/DSUBm/index.html)  | The Document Subscription for Mobile (DSUBm) Profile describes the use of document subscription and notification mechanisms for RESTful applications. In a similar way to the DSUB Profile, a subscription is made in order to receive a notification when a document publication event matches the criteria expressed in the subscription. |

### Audit

| Producer | Consumer | Name | Description |
|--
| &#10003; |  | [IHE Basic Audit Log Patterns (BALP)](https://profiles.ihe.net/ITI/BALP/) | The Basic Audit Log Patterns (BALP) Implementation Guide is a Content Profile that defines some basic and reusable AuditEvent patterns. This includes basic audit log profiles for FHIR RESTful operations to be used when there is not a more specific audit event defined. A focus is on enabling Privacy centric AuditEvent logs that hold well-formed indication of the Patient when they are the subject of the activity being recorded in the log. Where a more specific audit event can be defined, it should be derived off of these basic patterns. |

### Security and Application Launch

| Producer | Consumer | Name | Description |
|--
| &#10003; |  | [SMART App Launch](https://www.hl7.org/fhir/smart-app-launch/) | This implementation guide describes a set of foundational patterns based on OAuth 2.0 for client applications to authorize, authenticate, and integrate with FHIR-based data systems. The patterns defined in this specification are introduced in the sections below. For background on SMART Health IT, see smarthealthit.org. |
| &#10003; |  | [IHE Internet User Authorization (IUA)](https://profiles.ihe.net/ITI/IUA/index.html) | This profile is motivated by customer requirements for authorizing network transactions when using HTTP RESTful transports. IHE has authorization profiles for the Web Services and SOAP based transactions, and this profile provides an authorization profile for the HTTP RESTful transactions.

### Care Directory Services

| Producer | Consumer | Name | Description |
|--
| &#10003; |  | [IHE Mobile Care Services Discovery (mCSD)](https://profiles.ihe.net/ITI/mCSD/index.html) | The Mobile Care Services Discovery (mCSD) Profile supports RESTful queries across related care services resources. The loosely coupled design and flexible querying capability of the mCSD Profile means it can be deployed within a variety of eHealth architectures and support a wide array of care workflows. |


