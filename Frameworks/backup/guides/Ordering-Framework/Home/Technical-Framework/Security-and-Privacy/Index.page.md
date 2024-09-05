## {{page-title}}

<div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-information"></i><b> Important:</b> The content on these pages have not been approved or adopted by NHS England.</div>

### Security

- [Authentication (OpenID)](https://openid.net/) OpenID is a standard to help people assert their identity wherever they choose. 
    - [NHS Login](https://www.nhs.uk/nhs-services/online-services/nhs-login/) Authentication of a citizen (patient) identity
    - [Care Identity Service](https://digital.nhs.uk/services/identity-and-access-management/national-care-identity-service) The NHS Care Identity Service makes use of current technologies and Smartcards to allow health and care professionals in England to authenticate their identity when access national clinical information systems.

- [Authorization (OAuth2)](https://oauth.net/2/) OAuth 2.0 is the industry-standard protocol for authorization (it is not an authentication protocol). OAuth 2.0 focuses on client developer simplicity while providing specific authorization flows for web applications, desktop applications, mobile phones, and living room devices. This specification and its extensions are being developed within the IETF OAuth Working Group.

    - [SMART App Launch](https://www.hl7.org/fhir/smart-app-launch/) This implementation guide describes a set of foundational patterns based on [OAuth 2.0](https://datatracker.ietf.org/doc/html/rfc6749) for client applications to authorize, authenticate, and integrate with FHIR-based data systems. The patterns defined in this specification are introduced in the sections below. For background on SMART Health IT, see [smarthealthit.org](smarthealthit.org).

    - [OpenID HEART](https://openid.net/wg/heart/) The HEART working group intends to harmonize and develop a set of privacy and security specifications that enable an individual to control the authorization of access to RESTful health-related data sharing APIs, and to facilitate interoperable implementations of these specifications by others.

### Consent

Is some good resources from WSO2 https://www.youtube.com/watch?v=99czzTBm8z0 

### Provenance

Possibly could include this here https://developer.nhs.uk/apis/spine-core/security_jwt.html

### Audit

- [IHE Audit Trail and Node Authentication (ATNA)](https://www.ihe.net/uploadedFiles/Documents/ITI/IHE_ITI_Suppl_RESTful-ATNA.pdf) Event logging is a system facility that is used by healthcare applications and other applications.

- [IHE Basic Audit Log Patterns (BALP)](https://profiles.ihe.net/ITI/BALP/index.html) The Basic Audit Log Patterns (BALP) Implementation Guide is a Content Profile that defines some basic and reusable AuditEvent patterns. This includes basic audit log profiles for FHIR RESTful operations to be used when there is not a more specific audit event defined. A focus is on enabling Privacy centric AuditEvent logs that hold well-formed indication of the Patient when they are the subject of the activity being recorded in the log. Where a more specific audit event can be defined, it should be derived off of these basic patterns.

