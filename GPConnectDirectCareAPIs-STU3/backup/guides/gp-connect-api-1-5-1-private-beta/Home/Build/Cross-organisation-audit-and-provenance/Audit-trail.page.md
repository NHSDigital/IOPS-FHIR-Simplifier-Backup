## {{page-title}}

>Important: As the GP Connect APIs are commissioned under the GPSoC framework, provider and consumer systems are expected to follow the standard ‘IG Requirements for GP Systems V4’ and ‘GP Systems Interface Mechanism’ requirements. 

For implementers that don’t have access to the GPSoC Framework / ‘IG Requirements for GP Systems V4’ requirements then the following extract of requirements covers the main audit trail requirements:

- provider systems **SHALL** record in an audit trail all access and data changes within the system as a result of API activity in the same way that internal access and changes are required to be recorded

- provider systems **SHALL** ensure that all API transactions are recorded in an audit trail and that audit trails must be subject to the standard IG audit requirements as defined in ‘IG Requirements for GP Systems V4’ or as subsequently amended

- provider systems **SHALL** ensure failed or rejected API transactions are recorded with the same detail as for successful API requests, with error codes as per the [error handling guidance](https://simplifier.net/guide/gp-connect-access-record-structured/Home/Build/Error-handling?version=current)

Audit trail records **SHALL** include the following minimum information:

- a record of the user identity - this is the User ID, Name, Role profile (including Role and Organisation, URP id when Smartcard authenticated) attribute values, obtained from the user’s session structure
- a record of the identity of the authority – the person authorising the entry of or access to data (if different from the user)
- the date and time on which the event occurred
- details of the nature of the audited event and the identity of the associated data (for example, patient ID, message ID) of the audited event
- a sequence number to protect against malicious attempts to subvert the audit trail by, for example, altering the system date
- audit trail records **SHOULD** include details of the end-user device (or system) involved in the recorded activity

Audit trails **SHALL** be enabled at all times and there shall be no means for users, or any other individuals, to disable any audit trail.

>Note: Whilst some details (such as name, role) associated with individual users are likely to change over time, the display of user information must reflect the state of such information as it was at the time of the associated event (such as data entry).