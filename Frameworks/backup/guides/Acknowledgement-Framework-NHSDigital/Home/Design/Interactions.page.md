## {{page-title}}

<div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b> Important:</b> The Acknowledgement Framework is currently a draft version. Please contact the <a href="mailto:interoperabilityteam@nhs.net?subject=Acknowledgement Framework">Interoperability Standards Team</a> if you are interested to discuss this solution for your use case.</div>

To claim self-conformance of implementation of the Acknowledgement Framework, the following system interactions shall be supported where appropriate.

**Table column titles:**<br />
**mh-r-r.value - messageheader-response-request.value**<br />
**MH.response.code - MessageHeader.response.code**<br />
**OO.issue.severity - OperationOutcome.issue.severity**<br />
**OO.issue.code - OperationOutcome.issue.code**<br />

| ID | Paradigm | mh-r-r.value | MH.response.<br />code | OO.issue.<br />severity | OO.issue.<br />code | System Interaction Scenario |
| -- | -- | -- | -- | -- | -- | -- |
| 1.1.1 | Messaging | always | ok | | | System A sends a Message to System B where messageheader-response-request.value is 'always'. System B receives the Message and determines that the Message has no technical issues. System B responds with a Message where MessageHeader.response.code is 'ok'. |
| 1.1.2 | Messaging | always | ok | information | informational | System A sends a Message to System B where messageheader-response-request.value is 'always'. System B receives the Message and determines that the Message has no technical issues. However, System B wants to make System A aware that there will be server maintenance. System B responds with a Message where MessageHeader.response.code is 'ok', OperationOutcome.issue.severity is ‘information’ and OperationOutcome.issue.code is ‘informational’. |
| 1.1.3 | Messaging | always | ok | warning | informational | System A sends a Message to System B where messageheader-response-request.value is 'always'. System B receives the Message and determines that the Message has no technical issues. However, System B wants to make System A aware that it did not include a photo attachment of the patient in the Patient resource despite the fact this should have been included. As this is not a mandatory element, System B accepts the Message, to avoid any delays. System B responds with a Message where MessageHeader.response.code is 'ok', OperationOutcome.issue.severity is ‘warning’ and OperationOutcome.issue.code is ‘informational’. |
| 1.1.4 | Messaging | always | transient-error | fatal | transient | System A sends a Message to System B where messageheader-response-request.value is 'always'. System B receives the Message but is unable to process it because of a transient issue. The transient issue is either unknown or does not fit into the other available transient sub-error codes. System B responds with a Message where MessageHeader.response.code is ‘transient-error’, OperationOutcome.issue.severity is ‘fatal’ and OperationOutcome.issue.code is ‘transient’. |
| 1.1.5 | Messaging | always | transient-error | fatal | lock-error | System A sends a Message to System B where messageheader-response-request.value is 'always'. System B receives the Message but is unable to process it because there is a record locking failure within the database. System B responds with a Message where MessageHeader.response.code is ‘transient-error’, OperationOutcome.issue.severity is ‘fatal’ and OperationOutcome.issue.code is ‘lock-error’. |
| 1.1.6 | Messaging | always | transient-error | fatal | no-store | System A sends a Message to System B where messageheader-response-request.value is 'always'. System B receives the Message but is unable to process it because the database is unavailable because it is down for maintenance. System B response with a Message where MessageHeader.response.code is ‘transient-error’, OperationOutcome.issue.severity is ‘fatal’ and OperationOutcome.issue.code is ‘no-store’. |
| 1.1.7 | Messaging | always | transient-error | fatal | exception | System A sends a Message to System B where messageheader-response-request.value is 'always'. System B receives the Message but is unable to process it because there is an unexpected internal error on the server. System B response with a Message where MessageHeader.response.code is ‘transient-error’, OperationOutcome.issue.severity is ‘fatal’ and OperationOutcome.issue.code is ‘exception’. |
| 1.1.8 | Messaging | always | transient-error | fatal | timeout | System A sends a Message to System B where messageheader-response-request.value is 'always'. System B receives the Message but is unable to process it because an internal timeout on the server has occurred. System B response with a Message where MessageHeader.response.code is ‘transient-error’, OperationOutcome.issue.severity is ‘fatal’ and OperationOutcome.issue.code is ‘timeout’. |
| 1.1.9 | Messaging | always | transient-error | fatal | incomplete | System A sends a Message to System B where messageheader-response-request.value is 'always'. System B receives the Message but is unable to process it because some of the data sources could not be accessed within a suitable time. System B response with a Message where MessageHeader.response.code is ‘transient-error’, OperationOutcome.issue.severity is ‘fatal’ and OperationOutcome.issue.code is ‘incomplete’. |
| 1.1.10 | Messaging | always | transient-error | fatal | throttled | System A sends a Message to System where messageheader-response-request.value is 'always'. System B receives the Message but is unable to attempt to process it due to the server at System B being throttled because of a suspected Denial of Service attack. System B responds with a Message where MessageHeader.response.code is 'transient-error', OperationOutcome.issue.severity is 'fatal', and OperationOutcome.issue.code is 'throttled'. |
| 1.1.11 | Messaging | always | fatal-error | fatal OR error | invalid | System A sends a Message to System where messageheader-response-request.value is 'always'. System B receives the Message but identifies that the content of the Message is invalid against the FHIR specification or a profile. The invalid content issue is either not specifically known or does not fit with existing sub-error codes. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is 'invalid'. |
| 1.1.12 | Messaging | always | fatal-error | fatal OR error | structure | System A sends a Message to System where messageheader-response-request.value is 'always'. System B receives the Message but identifies that there is a structural issue within the Message. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is 'structure'. |
| 1.1.13 | Messaging | always | fatal-error | fatal OR error | required | System A sends a Message to System where messageheader-response-request.value is 'always'. System B receives the Message but identifies that a required element is missing within the Message. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is 'required'. |
| 1.1.14 | Messaging | always | fatal-error | fatal OR error | value | System A sends a Message to System where messageheader-response-request.value is 'always'. System B receives the Message but identifies that an element or header value is invalid within the Message. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is 'value'. |
| 1.1.15 | Messaging | always | fatal-error | fatal OR error | invarient | System A sends a Message to System where messageheader-response-request.value is 'always'. System B receives the Message but identifies that a content validation rule failed against the content within the Message. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is 'invarient'. |
| 1.1.16 | Messaging | always | fatal-error | fatal OR error | security | System A sends a Message to System where messageheader-response-request.value is 'always'. System B identifies that there is a security issue. The specific issue is either not known or does not fit with existing sub-error codes. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is 'security'. |
| 1.1.17 | Messaging | always | fatal-error | fatal OR error | login | System A sends a Message to System where messageheader-response-request.value is 'always'. System B identifies that the client had not initiated an authentication process. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is 'login'. |
| 1.1.18 | Messaging | always | fatal-error | fatal OR error | unknown | System A sends a Message to System where messageheader-response-request.value is 'always'. System B identifies that the user or system was unknown and not able to authenticate. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is 'unknown'. |
| 1.1.19 | Messaging | always | fatal-error | fatal OR error | expired | System A sends a Message to System where messageheader-response-request.value is 'always'. System B identifies that the user session has expired. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is 'expired'. |
| 1.1.20 | Messaging | always | fatal-error | fatal OR error | forbidden | System A sends a Message to System where messageheader-response-request.value is 'always'. System B identifies that the user does not have the rights to perform the action. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is 'forbidden'. |
| 1.1.21 | Messaging | always | fatal-error | fatal OR error | suppressed | System A sends a Message to System where messageheader-response-request.value is 'always'. System B identifies that some information cannot, or might not, be able to be retuned to System A due to business, consent, privacy, or access rules. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is 'suppressed'. |
| 1.1.22 | Messaging | always | fatal-error | fatal OR error | processing | System A sends a Message to System where messageheader-response-request.value is 'always'. System B is unable to fully process the request. The specific reason is either unknown or does not fit with existing sub-error codes. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is 'processing'. |
| 1.1.23 | Messaging | always | fatal-error | fatal OR error | not-supported | System A sends a Message to System where messageheader-response-request.value is 'always'. System B is unable to process the Message because an interaction, operation, resource, or profile is not supported. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is 'not-supported'. |
| 1.1.24 | Messaging | always | fatal-error | fatal OR error | duplicate | System A sends a Message to System where messageheader-response-request.value is 'always'. System B is unable to process the Message because an attempt was made to duplicate a record. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is ‘duplicate’. |
| 1.1.25 | Messaging | always | fatal-error | fatal OR error | multiple-matches | System A sends a Message to System where messageheader-response-request.value is 'always'. System B is unable to process the Message because multiple matching records were found when the operation required only one match. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is ‘multiple-matches’. |
| 1.1.26 | Messaging | always | fatal-error | fatal OR error | not-found | System A sends a Message to System where messageheader-response-request.value is 'always'. System B is unable to process the Message because the reference provided was not found. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is ‘not-found’. |
| 1.1.27 | Messaging | always | fatal-error | fatal OR error | deleted | System A sends a Message to System where messageheader-response-request.value is 'always'. System B is unable to process the Message because the reference pointed to content that has been deleted. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is ‘deleted’. |
| 1.1.28 | Messaging | always | fatal-error | fatal OR error | too-long | System A sends a Message to System where messageheader-response-request.value is 'always'. System B is unable to process the Message because the provided content in the Message is too long. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is ‘too-long’. |
| 1.1.29 | Messaging | always | fatal-error | fatal OR error | code-invalid | System A sends a Message to System where messageheader-response-request.value is 'always'. System B is unable to process the Message because there is an invalid code or system within the Message. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is ‘code-invalid’. |
| 1.1.30 | Messaging | always | fatal-error | fatal OR error | extension | System A sends a Message to System where messageheader-response-request.value is 'always'. System B is unable to process the Message because there is an unacceptable extension within the Message. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is ‘extension’. |
| 1.1.31 | Messaging | always | fatal-error | fatal OR error | too-costly | System A sends a Message to System where messageheader-response-request.value is 'always'. System B is unable to process the Message because the operation was stopped to protect server resources. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is ‘too-costly’. |
| 1.1.32 | Messaging | always | fatal-error | fatal OR error | business-rule | System A sends a Message to System where messageheader-response-request.value is 'always'. System B is unable to process the Message because there was a failure of a business rule. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is ‘business-rule’. |
| 1.1.33 | Messaging | always | fatal-error | fatal OR error | conflict | System A sends a Message to System where messageheader-response-request.value is 'always'. System B is unable to process the Message because there is an edit conflict. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is ‘conflict’. |
| 1.2.1 | Messaging | on-success | ok | | | System A sends a Message to System B where messageheader-response-request.value is 'on-success'. System B receives the Message and determines that the Message has no technical issues. System B responds with a Message where MessageHeader.response.code is 'ok'. |
| 1.2.2 | Messaging | on-success | ok | information | informational | System A sends a Message to System B where messageheader-response-request.value is 'on-success'. System B receives the Message and determines that the Message has no technical issues. However, System B wants to make System A aware that there will be server maintenance. System B responds with a Message where MessageHeader.response.code is 'ok', OperationOutcome.issue.severity is ‘information’ and OperationOutcome.issue.code is ‘informational’. |
| 1.2.3 | Messaging | on-success | ok | warning | informational | System A sends a Message to System B where messageheader-response-request.value is 'on-success'. System B receives the Message and determines that the Message has no technical issues. However, System B wants to make System A aware that it did not include a photo attachment of the patient in the Patient resource despite the fact this should have been included. As this is not a mandatory element, System B accepts the Message, to avoid any delays. System B responds with a Message where MessageHeader.response.code is 'ok', OperationOutcome.issue.severity is ‘warning’ and OperationOutcome.issue.code is ‘informational’. |
| 1.2.4 | Messaging | on-success | | | | System A sends a Message to System B where messageheader-response-request.value is 'on-success'. System B receives the Message but there is a technical issue where a mandatory element is missing. However, System B does NOT send an acknowledgement. |
| 1.2.5 | Messaging | on-success | | | | System A sends a Message to System B where messageheader-response-request.value is 'on-success'. System B receives the Message but is unable to process it because there is an unexpected internal error on the server. However, System B does NOT send an acknowledgement. |
| 1.3.1 | Messaging | on-error | | | | System A sends a Message to System B where messageheader-response-request.value is 'on-error'. System B receives the Message and determines that the Message has no technical issues. However, System B does NOT send an acknowledgement. |
| 1.3.2 | Messaging | on-error | | | | System A sends a Message to System B where messageheader-response-request.value is 'on-error'. System B receives the Message and determines that the Message has no technical issues. There is planned server maintenance. However, System B does NOT send an acknowledgement and therefore unable to provide information about the planned server maintenance. |
| 1.3.3 | Messaging | on-error | | | | System A sends a Message to System B where messageheader-response-request.value is 'on-error'. System B receives the Message and determines that the Message has no technical issues. However, System B expected System A to include a photo attachment of the patient in the Patient resource despite the fact it is not mandatory. As this is not a mandatory element, System B accepts the Message, to avoid any delays. However, System B does NOT send an acknowledgement and therefore unable to provide information about the expected patient photo attachment that was expected. |
| 1.3.4 | Messaging | on-error | transient-error | fatal | transient | System A sends a Message to System B where messageheader-response-request.value is 'on-error'. System B receives the Message but is unable to process it because of a transient issue. The transient issue is either unknown or does not fit into the other available transient sub-error codes. System B responds with a Message where MessageHeader.response.code is ‘transient-error’, OperationOutcome.issue.severity is ‘fatal’ and OperationOutcome.issue.code is ‘transient’. |
| 1.3.5 | Messaging | on-error | transient-error | fatal | lock-error | System A sends a Message to System B where messageheader-response-request.value is 'on-error'. System B receives the Message but is unable to process it because there is a record locking failure within the database. System B responds with a Message where MessageHeader.response.code is ‘transient-error’, OperationOutcome.issue.severity is ‘fatal’ and OperationOutcome.issue.code is ‘lock-error’. |
| 1.3.6 | Messaging | on-error | transient-error | fatal | no-store | System A sends a Message to System B where messageheader-response-request.value is on-error. System B receives the Message but is unable to process it because the database is unavailable because it is down for maintenance. System B response with a Message where MessageHeader.response.code is ‘transient-error’, OperationOutcome.issue.severity is ‘fatal’ and OperationOutcome.issue.code is ‘no-store’. |
| 1.3.7 | Messaging | on-error | transient-error | fatal | exception | System A sends a Message to System B where messageheader-response-request.value is 'on-error'. System B receives the Message but is unable to process it because there is an unexpected internal error on the server. System B response with a Message where MessageHeader.response.code is ‘transient-error’, OperationOutcome.issue.severity is ‘fatal’ and OperationOutcome.issue.code is ‘exception’. |
| 1.3.8 | Messaging | on-error | transient-error | fatal | timeout | System A sends a Message to System B where messageheader-response-request.value is 'on-error'. System B receives the Message but is unable to process it because an internal timeout on the server has occurred. System B response with a Message where MessageHeader.response.code is ‘transient-error’, OperationOutcome.issue.severity is ‘fatal’ and OperationOutcome.issue.code is ‘timeout’. |
| 1.3.9 | Messaging | on-error | transient-error | fatal | incomplete | System A sends a Message to System B where messageheader-response-request.value is 'on-error'. System B receives the Message but is unable to process it because some of the data sources could not be accessed within a suitable time. System B response with a Message where MessageHeader.response.code is ‘transient-error’, OperationOutcome.issue.severity is ‘fatal’ and OperationOutcome.issue.code is ‘incomplete’. |
| 1.3.10 | Messaging | on-error | transient-error | fatal | throttled | System A sends a Message to System where messageheader-response-request.value is 'on-error'. System B receives the Message but is unable to attempt to process it due to the server at System B being throttled because of a suspected Denial of Service attack. System B responds with a Message where MessageHeader.response.code is 'transient-error', OperationOutcome.issue.severity is 'fatal', and OperationOutcome.issue.code is 'throttled'. |
| 1.3.11 | Messaging | on-error | fatal-error | fatal OR error | invalid | System A sends a Message to System where messageheader-response-request.value is 'on-error'. System B receives the Message but identifies that the content of the Message is invalid against the FHIR specification or a profile. The invalid content issue is either not specifically known or does not fit with existing sub-error codes. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is 'invalid'. |
| 1.3.12 | Messaging | on-error | fatal-error | fatal OR error | structure | System A sends a Message to System where messageheader-response-request.value is 'on-error'. System B receives the Message but identifies that there is a structural issue within the Message. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is 'structure'. |
| 1.3.13 | Messaging | on-error | fatal-error | fatal OR error | required | System A sends a Message to System where messageheader-response-request.value is 'on-error'. System B receives the Message but identifies that a required element is missing within the Message. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is 'required'. |
| 1.3.14 | Messaging | on-error | fatal-error | fatal OR error | value | System A sends a Message to System where messageheader-response-request.value is 'on-error'. System B receives the Message but identifies that an element or header value is invalid within the Message. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is 'value'. |
| 1.3.15 | Messaging | on-error | fatal-error | fatal OR error | invarient | System A sends a Message to System where messageheader-response-request.value is 'on-error'. System B receives the Message but identifies that a content validation rule failed against the content within the Message. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is 'invarient'. |
| 1.3.16 | Messaging | on-error | fatal-error | fatal OR error | security | System A sends a Message to System where messageheader-response-request.value is 'on-error'. System B identifies that there is a security issue. The specific issue is either not known or does not fit with existing sub-error codes. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is 'security'. |
| 1.3.17 | Messaging | on-error | fatal-error | fatal OR error | login | System A sends a Message to System where messageheader-response-request.value is 'on-error'. System B identifies that the client had not initiated an authentication process. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is 'login'. |
| 1.3.18 | Messaging | on-error | fatal-error | fatal OR error | unknown | System A sends a Message to System where messageheader-response-request.value is 'on-error'. System B identifies that the user or system was unknown and not able to authenticate. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is 'unknown'. |
| 1.3.19 | Messaging | on-error | fatal-error | fatal OR error | expired | System A sends a Message to System where messageheader-response-request.value is 'on-error'. System B identifies that the user session has expired. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is 'expired'. |
| 1.3.20 | Messaging | on-error | fatal-error | fatal OR error | forbidden | System A sends a Message to System where messageheader-response-request.value is 'on-error'. System B identifies that the user does not have the rights to perform the action. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is 'forbidden'. |
| 1.3.21 | Messaging | on-error | fatal-error | fatal OR error | suppressed | System A sends a Message to System where messageheader-response-request.value is 'on-error'. System B identifies that some information cannot, or might not, be able to be retuned to System A due to business, consent, privacy, or access rules. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is 'suppressed'. |
| 1.3.22 | Messaging | on-error | fatal-error | fatal OR error | processing | System A sends a Message to System where messageheader-response-request.value is 'on-error'. System B is unable to fully process the request. The specific reason is either unknown or does not fit with existing sub-error codes. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is 'processing'. |
| 1.3.23 | Messaging | on-error | fatal-error | fatal OR error | not-supported | System A sends a Message to System where messageheader-response-request.value is 'on-error'. System B is unable to process the Message because an interaction, operation, resource, or profile is not supported. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is 'not-supported'. |
| 1.3.24 | Messaging | on-error | fatal-error | fatal OR error | duplicate | System A sends a Message to System where messageheader-response-request.value is 'on-error'. System B is unable to process the Message because an attempt was made to duplicate a record. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is ‘duplicate’. |
| 1.3.25 | Messaging | on-error | fatal-error | fatal OR error | multiple-matches | System A sends a Message to System where messageheader-response-request.value is 'on-error'. System B is unable to process the Message because multiple matching records were found when the operation required only one match. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is ‘multiple-matches’. |
| 1.3.26 | Messaging | on-error | fatal-error | fatal OR error | not-found | System A sends a Message to System where messageheader-response-request.value is 'on-error'. System B is unable to process the Message because the reference provided was not found. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is ‘not-found’. |
| 1.3.27 | Messaging | on-error | fatal-error | fatal OR error | deleted | System A sends a Message to System where messageheader-response-request.value is 'on-error'. System B is unable to process the Message because the reference pointed to content that has been deleted. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is ‘deleted’. |
| 1.3.28 | Messaging | on-error | fatal-error | fatal OR error | too-long | System A sends a Message to System where messageheader-response-request.value is 'on-error'. System B is unable to process the Message because the provided content in the Message is too long. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is ‘too-long’. |
| 1.3.29 | Messaging | on-error | fatal-error | fatal OR error | code-invalid | System A sends a Message to System where messageheader-response-request.value is 'on-error'. System B is unable to process the Message because there is an invalid code or system within the Message. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is ‘code-invalid’. |
| 1.3.30 | Messaging | on-error | fatal-error | fatal OR error | extension | System A sends a Message to System where messageheader-response-request.value is 'on-error'. System B is unable to process the Message because there is an unacceptable extension within the Message. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is ‘extension’. |
| 1.3.31 | Messaging | on-error | fatal-error | fatal OR error | too-costly | System A sends a Message to System where messageheader-response-request.value is 'on-error'. System B is unable to process the Message because the operation was stopped to protect server resources. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is ‘too-costly’. |
| 1.3.32 | Messaging | on-error | fatal-error | fatal OR error | business-rule | System A sends a Message to System where messageheader-response-request.value is 'on-error'. System B is unable to process the Message because there was a failure of a business rule. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is ‘business-rule’. |
| 1.3.33 | Messaging | on-error | fatal-error | fatal OR error | conflict | System A sends a Message to System where messageheader-response-request.value is 'on-error'. System B is unable to process the Message because there is an edit conflict. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is ‘conflict’. |
| 1.4.1 | Messaging | never | | | | System A sends a Message to System where messageheader-response-request.value is 'never'. System B receives the Message and determines that the Message has no technical issues. However, System B does NOT send an acknowledgement. |
| 1.4.2 | Messaging | never | | | | System A sends a Message to System where messageheader-response-request.value is 'never'. System B receives the Message but there is a technical issue where a mandatory element is missing. However, System B does NOT send an acknowledgement. |
| 1.4.3 | Messaging | never | | | | System A sends a Message to System where messageheader-response-request.value is 'never'. System B receives the Message but there is an unexpected internal error on the server. However, System B does NOT send an acknowledgement. |
| 2.1.1 | Documents | To be done | To be done | To be done | To be done | To be done |
| 3.1.1 | RESTful | To be done | To be done | To be done | To be done | To be done |

<br /><br />

## Diagrams

| ID | System Interaction Scenario | Diagram |
| -- | --------------------------- | ------- |
| 1.1.1 | System A sends a Message to System B where messageheader-response-request.value is 'always'. System B receives the Message and determines that the Message has no technical issues. System B responds with a Message where MessageHeader.response.code is 'ok'. | <plantuml>
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **always** 
...
end note
receiver --> sender: Message acknowledgement
note right
MessageHeader.id: **0002**
MessageHeader.extension.
messageheader-response-request.
valueCode: **never**
MessageHeader.response.identifier: **0001**
MessageHeader.response.code: **ok**
...
end note
</plantuml> |
| 1.1.2 | System A sends a Message to System B where messageheader-response-request.value is 'always'. System B receives the Message and determines that the Message has no technical issues. However, System B wants to make System A aware that there will be server maintenance. System B responds with a Message where MessageHeader.response.code is 'ok', OperationOutcome.issue.severity is ‘information’ and OperationOutcome.issue.code is ‘informational’. | <plantuml>
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **always** 
...
end note
receiver --> sender: Message acknowledgement
note right
MessageHeader.id: **0002**
MessageHeader.extension.
messageheader-response-request.
valueCode: **never**
MessageHeader.response.identifier: **0001**
MessageHeader.response.code: **ok**
OperationOutcome.issue.severity: **information**
OperationOutcome.issue.code: **informational**
...
end note
</plantuml> |
| 1.1.3 | System A sends a Message to System B where messageheader-response-request.value is 'always'. System B receives the Message and determines that the Message has no technical issues. However, System B wants to make System A aware that it did not include a photo attachment of the patient in the Patient resource despite the fact this should have been included. As this is not a mandatory element, System B accepts the Message, to avoid any delays. System B responds with a Message where MessageHeader.response.code is 'ok', OperationOutcome.issue.severity is ‘warning’ and OperationOutcome.issue.code is ‘informational’. | <plantuml>
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **always** 
...
end note
receiver --> sender: Message acknowledgement
note right
MessageHeader.id: **0002**
MessageHeader.extension.
messageheader-response-request.
valueCode: **never**
MessageHeader.response.identifier: **0001**
MessageHeader.response.code: **ok**
OperationOutcome.issue.severity: **warning**
OperationOutcome.issue.code: **informational**
...
end note
</plantuml> |
| 1.1.4 | System A sends a Message to System B where messageheader-response-request.value is 'always'. System B receives the Message but is unable to process it because of a transient issue. The transient issue is either unknown or does not fit into the other available transient sub-error codes. System B responds with a Message where MessageHeader.response.code is ‘transient-error’, OperationOutcome.issue.severity is ‘fatal’ and OperationOutcome.issue.code is ‘transient’. | <plantuml>
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **always** 
...
end note
receiver --> sender: Message acknowledgement
note right
MessageHeader.id: **0002**
MessageHeader.extension.
messageheader-response-request.
valueCode: **never**
MessageHeader.response.identifier: **0001**
MessageHeader.response.code: **transient-error**
OperationOutcome.issue.severity: **fatal**
OperationOutcome.issue.code: **transient**
...
end note
</plantuml> |
| 1.1.5 | System A sends a Message to System B where messageheader-response-request.value is 'always'. System B receives the Message but is unable to process it because there is a record locking failure within the database. System B responds with a Message where MessageHeader.response.code is ‘transient-error’, OperationOutcome.issue.severity is ‘fatal’ and OperationOutcome.issue.code is ‘lock-error’. | <plantuml>
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **always** 
...
end note
receiver --> sender: Message acknowledgement
note right
MessageHeader.id: **0002**
MessageHeader.extension.
messageheader-response-request.
valueCode: **never**
MessageHeader.response.identifier: **0001**
MessageHeader.response.code: **transient-error**
OperationOutcome.issue.severity: **fatal**
OperationOutcome.issue.code: **lock-error**
...
end note
</plantuml> |
| 1.1.6 | System A sends a Message to System B where messageheader-response-request.value is 'always'. System B receives the Message but is unable to process it because the database is unavailable because it is down for maintenance. System B response with a Message where MessageHeader.response.code is ‘transient-error’, OperationOutcome.issue.severity is ‘fatal’ and OperationOutcome.issue.code is ‘no-store’. | <plantuml>
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **always** 
...
end note
receiver --> sender: Message acknowledgement
note right
MessageHeader.id: **0002**
MessageHeader.extension.
messageheader-response-request.
valueCode: **never**
MessageHeader.response.identifier: **0001**
MessageHeader.response.code: **transient-error**
OperationOutcome.issue.severity: **fatal**
OperationOutcome.issue.code: **no-store**
...
end note
</plantuml> |
| 1.1.7 | System A sends a Message to System B where messageheader-response-request.value is 'always'. System B receives the Message but is unable to process it because there is an unexpected internal error on the server. System B response with a Message where MessageHeader.response.code is ‘transient-error’, OperationOutcome.issue.severity is ‘fatal’ and OperationOutcome.issue.code is ‘exception’. | <plantuml>
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **always** 
...
end note
receiver --> sender: Message acknowledgement
note right
MessageHeader.id: **0002**
MessageHeader.extension.
messageheader-response-request.
valueCode: **never**
MessageHeader.response.identifier: **0001**
MessageHeader.response.code: **transient-error**
OperationOutcome.issue.severity: **fatal**
OperationOutcome.issue.code: **exception**
...
end note
</plantuml> |
| 1.1.8 | System A sends a Message to System B where messageheader-response-request.value is 'always'. System B receives the Message but is unable to process it because an internal timeout on the server has occurred. System B response with a Message where MessageHeader.response.code is ‘transient-error’, OperationOutcome.issue.severity is ‘fatal’ and OperationOutcome.issue.code is ‘timeout’. | <plantuml>
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **always** 
...
end note
receiver --> sender: Message acknowledgement
note right
MessageHeader.id: **0002**
MessageHeader.extension.
messageheader-response-request.
valueCode: **never**
MessageHeader.response.identifier: **0001**
MessageHeader.response.code: **transient-error**
OperationOutcome.issue.severity: **fatal**
OperationOutcome.issue.code: **timeout**
...
end note
</plantuml> |
| 1.1.9 | System A sends a Message to System B where messageheader-response-request.value is 'always'. System B receives the Message but is unable to process it because some of the data sources could not be accessed within a suitable time. System B response with a Message where MessageHeader.response.code is ‘transient-error’, OperationOutcome.issue.severity is ‘fatal’ and OperationOutcome.issue.code is ‘incomplete’. | <plantuml>
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **always** 
...
end note
receiver --> sender: Message acknowledgement
note right
MessageHeader.id: **0002**
MessageHeader.extension.
messageheader-response-request.
valueCode: **never**
MessageHeader.response.identifier: **0001**
MessageHeader.response.code: **transient-error**
OperationOutcome.issue.severity: **fatal**
OperationOutcome.issue.code: **incomplete**
...
end note
</plantuml> |
| 1.1.10 | System A sends a Message to System where messageheader-response-request.value is 'always'. System B receives the Message but is unable to attempt to process it due to the server at System B being throttled because of a suspected Denial of Service attack. System B responds with a Message where MessageHeader.response.code is 'transient-error', OperationOutcome.issue.severity is 'fatal', and OperationOutcome.issue.code is 'throttled'. | <plantuml>
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **always** 
...
end note
receiver --> sender: Message acknowledgement
note right
MessageHeader.id: **0002**
MessageHeader.extension.
messageheader-response-request.
valueCode: **never**
MessageHeader.response.identifier: **0001**
MessageHeader.response.code: **transient-error**
OperationOutcome.issue.severity: **fatal**
OperationOutcome.issue.code: **throttled**
...
end note
</plantuml> |
| 1.1.11 | System A sends a Message to System where messageheader-response-request.value is 'always'. System B receives the Message but identifies that the content of the Message is invalid against the FHIR specification or a profile. The invalid content issue is either not specifically known or does not fit with existing sub-error codes. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is 'invalid'. | <plantuml>
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **always** 
...
end note
receiver --> sender: Message acknowledgement
note right
MessageHeader.id: **0002**
MessageHeader.extension.
messageheader-response-request.
valueCode: **never**
MessageHeader.response.identifier: **0001**
MessageHeader.response.code: **fatal-error**
OperationOutcome.issue.severity: **fatal OR error**
OperationOutcome.issue.code: **invalid**
...
end note
</plantuml> |
| 1.1.12 | System A sends a Message to System where messageheader-response-request.value is 'always'. System B receives the Message but identifies that there is a structural issue within the Message. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is 'structure'. | <plantuml>
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **always** 
...
end note
receiver --> sender: Message acknowledgement
note right
MessageHeader.id: **0002**
MessageHeader.extension.
messageheader-response-request.
valueCode: **never**
MessageHeader.response.identifier: **0001**
MessageHeader.response.code: **fatal-error**
OperationOutcome.issue.severity: **fatal OR error**
OperationOutcome.issue.code: **structure**
...
end note
</plantuml> |
| 1.1.13 | System A sends a Message to System where messageheader-response-request.value is 'always'. System B receives the Message but identifies that a required element is missing within the Message. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is 'required'. | <plantuml>
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **always** 
...
end note
receiver --> sender: Message acknowledgement
note right
MessageHeader.id: **0002**
MessageHeader.extension.
messageheader-response-request.
valueCode: **never**
MessageHeader.response.identifier: **0001**
MessageHeader.response.code: **fatal-error**
OperationOutcome.issue.severity: **fatal OR error**
OperationOutcome.issue.code: **required**
...
end note
</plantuml> |
| 1.1.14 | System A sends a Message to System where messageheader-response-request.value is 'always'. System B receives the Message but identifies that an element or header value is invalid within the Message. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is 'value'. | <plantuml>
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **always** 
...
end note
receiver --> sender: Message acknowledgement
note right
MessageHeader.id: **0002**
MessageHeader.extension.
messageheader-response-request.
valueCode: **never**
MessageHeader.response.identifier: **0001**
MessageHeader.response.code: **fatal-error**
OperationOutcome.issue.severity: **fatal OR error**
OperationOutcome.issue.code: **value**
...
end note
</plantuml> |
| 1.1.15 | System A sends a Message to System where messageheader-response-request.value is 'always'. System B receives the Message but identifies that a content validation rule failed against the content within the Message. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is 'invarient'. | <plantuml>
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **always** 
...
end note
receiver --> sender: Message acknowledgement
note right
MessageHeader.id: **0002**
MessageHeader.extension.
messageheader-response-request.
valueCode: **never**
MessageHeader.response.identifier: **0001**
MessageHeader.response.code: **fatal-error**
OperationOutcome.issue.severity: **fatal OR error**
OperationOutcome.issue.code: **invarient**
...
end note
</plantuml> |
| 1.1.16 | System A sends a Message to System where messageheader-response-request.value is 'always'. System B identifies that there is a security issue. The specific issue is either not known or does not fit with existing sub-error codes. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is 'security'. | <plantuml>
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **always** 
...
end note
receiver --> sender: Message acknowledgement
note right
MessageHeader.id: **0002**
MessageHeader.extension.
messageheader-response-request.
valueCode: **never**
MessageHeader.response.identifier: **0001**
MessageHeader.response.code: **fatal-error**
OperationOutcome.issue.severity: **fatal OR error**
OperationOutcome.issue.code: **security**
...
end note
</plantuml> |
| 1.1.17 | System A sends a Message to System where messageheader-response-request.value is 'always'. System B identifies that the client had not initiated an authentication process. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is 'login'. | <plantuml>
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **always** 
...
end note
receiver --> sender: Message acknowledgement
note right
MessageHeader.id: **0002**
MessageHeader.extension.
messageheader-response-request.
valueCode: **never**
MessageHeader.response.identifier: **0001**
MessageHeader.response.code: **fatal-error**
OperationOutcome.issue.severity: **fatal OR error**
OperationOutcome.issue.code: **login**
...
end note
</plantuml> |
| 1.1.18 | System A sends a Message to System where messageheader-response-request.value is 'always'. System B identifies that the user or system was unknown and not able to authenticate. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is 'unknown'. | <plantuml>
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **always** 
...
end note
receiver --> sender: Message acknowledgement
note right
MessageHeader.id: **0002**
MessageHeader.extension.
messageheader-response-request.
valueCode: **never**
MessageHeader.response.identifier: **0001**
MessageHeader.response.code: **fatal-error**
OperationOutcome.issue.severity: **fatal OR error**
OperationOutcome.issue.code: **unknown**
...
end note
</plantuml> |
| 1.1.19 | System A sends a Message to System where messageheader-response-request.value is 'always'. System B identifies that the user session has expired. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is 'expired'. | <plantuml>
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **always** 
...
end note
receiver --> sender: Message acknowledgement
note right
MessageHeader.id: **0002**
MessageHeader.extension.
messageheader-response-request.
valueCode: **never**
MessageHeader.response.identifier: **0001**
MessageHeader.response.code: **fatal-error**
OperationOutcome.issue.severity: **fatal OR error**
OperationOutcome.issue.code: **expired**
...
end note
</plantuml> |
| 1.1.20 | System A sends a Message to System where messageheader-response-request.value is 'always'. System B identifies that the user does not have the rights to perform the action. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is 'forbidden'. | <plantuml>
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **always** 
...
end note
receiver --> sender: Message acknowledgement
note right
MessageHeader.id: **0002**
MessageHeader.extension.
messageheader-response-request.
valueCode: **never**
MessageHeader.response.identifier: **0001**
MessageHeader.response.code: **fatal-error**
OperationOutcome.issue.severity: **fatal OR error**
OperationOutcome.issue.code: **forbidden**
...
end note
</plantuml> |
| 1.1.21 | System A sends a Message to System where messageheader-response-request.value is 'always'. System B identifies that some information cannot, or might not, be able to be retuned to System A due to business, consent, privacy, or access rules. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is 'suppressed'. | <plantuml>
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **always** 
...
end note
receiver --> sender: Message acknowledgement
note right
MessageHeader.id: **0002**
MessageHeader.extension.
messageheader-response-request.
valueCode: **never**
MessageHeader.response.identifier: **0001**
MessageHeader.response.code: **fatal-error**
OperationOutcome.issue.severity: **fatal OR error**
OperationOutcome.issue.code: **suppressed**
...
end note
</plantuml> |
| 1.1.22 | System A sends a Message to System where messageheader-response-request.value is 'always'. System B is unable to fully process the request. The specific reason is either unknown or does not fit with existing sub-error codes. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is 'processing'. | <plantuml>
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **always** 
...
end note
receiver --> sender: Message acknowledgement
note right
MessageHeader.id: **0002**
MessageHeader.extension.
messageheader-response-request.
valueCode: **never**
MessageHeader.response.identifier: **0001**
MessageHeader.response.code: **fatal-error**
OperationOutcome.issue.severity: **fatal OR error**
OperationOutcome.issue.code: **processing**
...
end note
</plantuml> |
| 1.1.23 | System A sends a Message to System where messageheader-response-request.value is 'always'. System B is unable to process the Message because an interaction, operation, resource, or profile is not supported. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is 'not-supported'. | <plantuml>
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **always** 
...
end note
receiver --> sender: Message acknowledgement
note right
MessageHeader.id: **0002**
MessageHeader.extension.
messageheader-response-request.
valueCode: **never**
MessageHeader.response.identifier: **0001**
MessageHeader.response.code: **fatal-error**
OperationOutcome.issue.severity: **fatal OR error**
OperationOutcome.issue.code: **not-supported**
...
end note
</plantuml> |
| 1.1.24 | System A sends a Message to System where messageheader-response-request.value is 'always'. System B is unable to process the Message because an attempt was made to duplicate a record. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is ‘duplicate’. | <plantuml>
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **always** 
...
end note
receiver --> sender: Message acknowledgement
note right
MessageHeader.id: **0002**
MessageHeader.extension.
messageheader-response-request.
valueCode: **never**
MessageHeader.response.identifier: **0001**
MessageHeader.response.code: **fatal-error**
OperationOutcome.issue.severity: **fatal OR error**
OperationOutcome.issue.code: **duplicate**
...
end note
</plantuml> |
| 1.1.25 | System A sends a Message to System where messageheader-response-request.value is 'always'. System B is unable to process the Message because multiple matching records were found when the operation required only one match. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is ‘multiple-matches’. | <plantuml>
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **always** 
...
end note
receiver --> sender: Message acknowledgement
note right
MessageHeader.id: **0002**
MessageHeader.extension.
messageheader-response-request.
valueCode: **never**
MessageHeader.response.identifier: **0001**
MessageHeader.response.code: **fatal-error**
OperationOutcome.issue.severity: **fatal OR error**
OperationOutcome.issue.code: **multiple-matches**
...
end note
</plantuml> |
| 1.1.26 | System A sends a Message to System where messageheader-response-request.value is 'always'. System B is unable to process the Message because the reference provided was not found. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is ‘not-found’. | <plantuml>
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **always** 
...
end note
receiver --> sender: Message acknowledgement
note right
MessageHeader.id: **0002**
MessageHeader.extension.
messageheader-response-request.
valueCode: **never**
MessageHeader.response.identifier: **0001**
MessageHeader.response.code: **fatal-error**
OperationOutcome.issue.severity: **fatal OR error**
OperationOutcome.issue.code: **not-found**
...
end note
</plantuml> |
| 1.1.27 | System A sends a Message to System where messageheader-response-request.value is 'always'. System B is unable to process the Message because the reference pointed to content that has been deleted. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is ‘deleted’. | <plantuml>
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **always** 
...
end note
receiver --> sender: Message acknowledgement
note right
MessageHeader.id: **0002**
MessageHeader.extension.
messageheader-response-request.
valueCode: **never**
MessageHeader.response.identifier: **0001**
MessageHeader.response.code: **fatal-error**
OperationOutcome.issue.severity: **fatal OR error**
OperationOutcome.issue.code: **deleted**
...
end note
</plantuml> |
| 1.1.28 |  System A sends a Message to System where messageheader-response-request.value is 'always'. System B is unable to process the Message because the provided content in the Message is too long. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is ‘too-long’. | <plantuml>
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **always** 
...
end note
receiver --> sender: Message acknowledgement
note right
MessageHeader.id: **0002**
MessageHeader.extension.
messageheader-response-request.
valueCode: **never**
MessageHeader.response.identifier: **0001**
MessageHeader.response.code: **fatal-error**
OperationOutcome.issue.severity: **fatal OR error**
OperationOutcome.issue.code: **too-long**
...
end note
</plantuml> |
| 1.1.29 | System A sends a Message to System where messageheader-response-request.value is 'always'. System B is unable to process the Message because there is an invalid code or system within the Message. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is ‘code-invalid’. | <plantuml>
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **always** 
...
end note
receiver --> sender: Message acknowledgement
note right
MessageHeader.id: **0002**
MessageHeader.extension.
messageheader-response-request.
valueCode: **never**
MessageHeader.response.identifier: **0001**
MessageHeader.response.code: **fatal-error**
OperationOutcome.issue.severity: **fatal OR error**
OperationOutcome.issue.code: **code-invalid**
...
end note
</plantuml> |
| 1.1.30 | System A sends a Message to System where messageheader-response-request.value is 'always'. System B is unable to process the Message because there is an unacceptable extension within the Message. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is ‘extension’. | <plantuml>
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **always** 
...
end note
receiver --> sender: Message acknowledgement
note right
MessageHeader.id: **0002**
MessageHeader.extension.
messageheader-response-request.
valueCode: **never**
MessageHeader.response.identifier: **0001**
MessageHeader.response.code: **fatal-error**
OperationOutcome.issue.severity: **fatal OR error**
OperationOutcome.issue.code: **extension**
...
end note
</plantuml> | 
| 1.1.31 | System A sends a Message to System where messageheader-response-request.value is 'always'. System B is unable to process the Message because the operation was stopped to protect server resources. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is ‘too-costly’. |<plantuml>
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **always** 
...
end note
receiver --> sender: Message acknowledgement
note right
MessageHeader.id: **0002**
MessageHeader.extension.
messageheader-response-request.
valueCode: **never**
MessageHeader.response.identifier: **0001**
MessageHeader.response.code: **fatal-error**
OperationOutcome.issue.severity: **fatal OR error**
OperationOutcome.issue.code: **too-costly**
...
end note
</plantuml> |
| 1.1.32 | System A sends a Message to System where messageheader-response-request.value is 'always'. System B is unable to process the Message because there was a failure of a business rule. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is ‘business-rule’. | <plantuml>
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **always** 
...
end note
receiver --> sender: Message acknowledgement
note right
MessageHeader.id: **0002**
MessageHeader.extension.
messageheader-response-request.
valueCode: **never**
MessageHeader.response.identifier: **0001**
MessageHeader.response.code: **fatal-error**
OperationOutcome.issue.severity: **fatal OR error**
OperationOutcome.issue.code: **business-rule**
...
end note
</plantuml> |
| 1.1.33 | System A sends a Message to System where messageheader-response-request.value is 'always'. System B is unable to process the Message because there is an edit conflict. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is ‘conflict’. | <plantuml>
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **always** 
...
end note
receiver --> sender: Message acknowledgement
note right
MessageHeader.id: **0002**
MessageHeader.extension.
messageheader-response-request.
valueCode: **never**
MessageHeader.response.identifier: **0001**
MessageHeader.response.code: **fatal-error**
OperationOutcome.issue.severity: **fatal OR error**
OperationOutcome.issue.code: **conflict**
...
end note
</plantuml> |
| 1.2.1 | System A sends a Message to System B where messageheader-response-request.value is 'on-success'. System B receives the Message and determines that the Message has no technical issues. System B responds with a Message where MessageHeader.response.code is 'ok'. | <plantuml>
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **on-success** 
...
end note
receiver --> sender: Message acknowledgement
note right
MessageHeader.id: **0002**
MessageHeader.extension.
messageheader-response-request.
valueCode: **never**
MessageHeader.response.identifier: **0001**
MessageHeader.response.code: **ok**
...
end note
</plantuml> |
| 1.2.2 | System A sends a Message to System B where messageheader-response-request.value is 'on-success'. System B receives the Message and determines that the Message has no technical issues. However, System B wants to make System A aware that there will be server maintenance. System B responds with a Message where MessageHeader.response.code is 'ok', OperationOutcome.issue.severity is ‘information’ and OperationOutcome.issue.code is ‘informational’. | <plantuml>
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **on-success** 
...
end note
receiver --> sender: Message acknowledgement
note right
MessageHeader.id: **0002**
MessageHeader.extension.
messageheader-response-request.
valueCode: **never**
MessageHeader.response.identifier: **0001**
MessageHeader.response.code: **ok**
OperationOutcome.issue.severity: **information**
OperationOutcome.issue.code: **informational**
...
end note
</plantuml> |
| 1.2.3 | System A sends a Message to System B where messageheader-response-request.value is 'on-success'. System B receives the Message and determines that the Message has no technical issues. However, System B wants to make System A aware that it did not include a photo attachment of the patient in the Patient resource despite the fact this should have been included. As this is not a mandatory element, System B accepts the Message, to avoid any delays. System B responds with a Message where MessageHeader.response.code is 'ok', OperationOutcome.issue.severity is ‘warning’ and OperationOutcome.issue.code is ‘informational’. | <plantuml>
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **on-success** 
...
end note
receiver --> sender: Message acknowledgement
note right
MessageHeader.id: **0002**
MessageHeader.extension.
messageheader-response-request.
valueCode: **never**
MessageHeader.response.identifier: **0001**
MessageHeader.response.code: **ok**
OperationOutcome.issue.severity: **warning**
OperationOutcome.issue.code: **informational**
...
end note
</plantuml> |
| 1.2.4 | System A sends a Message to System B where messageheader-response-request.value is 'on-success'. System B receives the Message but there is a technical issue where a mandatory element is missing. However, System B does NOT send an acknowledgement. | <plantuml>
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **on-success** 
...
end note
</plantuml> |
| 1.2.5 | System A sends a Message to System B where messageheader-response-request.value is 'on-success'. System B receives the Message but is unable to process it because there is an unexpected internal error on the server. However, System B does NOT send an acknowledgement. | <plantuml>
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **on-success** 
...
end note
</plantuml> |
| 1.3.1 | System A sends a Message to System B where messageheader-response-request.value is 'on-error'. System B receives the Message and determines that the Message has no technical issues. However, System B does NOT send an acknowledgement. | <plantuml>
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **on-error** 
...
end note
</plantuml> |
| 1.3.2 | System A sends a Message to System B where messageheader-response-request.value is 'on-error'. System B receives the Message and determines that the Message has no technical issues. There is planned server maintenance. However, System B does NOT send an acknowledgement and therefore unable to provide information about the planned server maintenance. | <plantuml>
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **on-error** 
...
end note
</plantuml> |
| 1.3.3 | System A sends a Message to System B where messageheader-response-request.value is 'on-error'. System B receives the Message and determines that the Message has no technical issues. However, System B expected System A to include a photo attachment of the patient in the Patient resource despite the fact it is not mandatory. As this is not a mandatory element, System B accepts the Message, to avoid any delays. However, System B does NOT send an acknowledgement and therefore unable to provide information about the expected patient photo attachment that was expected. | <plantuml>
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **on-error** 
...
end note
</plantuml> |
| 1.3.4 | System A sends a Message to System B where messageheader-response-request.value is 'on-error'. System B receives the Message but is unable to process it because of a transient issue. The transient issue is either unknown or does not fit into the other available transient sub-error codes. System B responds with a Message where MessageHeader.response.code is ‘transient-error’, OperationOutcome.issue.severity is ‘fatal’ and OperationOutcome.issue.code is ‘transient’. | <plantuml>
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **on-error** 
...
end note
receiver --> sender: Message acknowledgement
note right
MessageHeader.id: **0002**
MessageHeader.extension.
messageheader-response-request.
valueCode: **never**
MessageHeader.response.identifier: **0001**
MessageHeader.response.code: **transient-error**
OperationOutcome.issue.severity: **fatal**
OperationOutcome.issue.code: **transient**
...
end note
</plantuml> |
| 1.3.5 | System A sends a Message to System B where messageheader-response-request.value is 'on-error'. System B receives the Message but is unable to process it because there is a record locking failure within the database. System B responds with a Message where MessageHeader.response.code is ‘transient-error’, OperationOutcome.issue.severity is ‘fatal’ and OperationOutcome.issue.code is ‘lock-error’. | <plantuml>
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **on-error** 
...
end note
receiver --> sender: Message acknowledgement
note right
MessageHeader.id: **0002**
MessageHeader.extension.
messageheader-response-request.
valueCode: **never**
MessageHeader.response.identifier: **0001**
MessageHeader.response.code: **transient-error**
OperationOutcome.issue.severity: **fatal**
OperationOutcome.issue.code: **lock-error**
...
end note
</plantuml> |
| 1.3.6 | System A sends a Message to System B where messageheader-response-request.value is on-error. System B receives the Message but is unable to process it because the database is unavailable because it is down for maintenance. System B response with a Message where MessageHeader.response.code is ‘transient-error’, OperationOutcome.issue.severity is ‘fatal’ and OperationOutcome.issue.code is ‘no-store’. | <plantuml>
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **on-error** 
...
end note
receiver --> sender: Message acknowledgement
note right
MessageHeader.id: **0002**
MessageHeader.extension.
messageheader-response-request.
valueCode: **never**
MessageHeader.response.identifier: **0001**
MessageHeader.response.code: **transient-error**
OperationOutcome.issue.severity: **fatal**
OperationOutcome.issue.code: **no-store**
...
end note
</plantuml> |
| 1.3.7 | System A sends a Message to System B where messageheader-response-request.value is 'on-error'. System B receives the Message but is unable to process it because there is an unexpected internal error on the server. System B response with a Message where MessageHeader.response.code is ‘transient-error’, OperationOutcome.issue.severity is ‘fatal’ and OperationOutcome.issue.code is ‘exception’. | <plantuml>
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **on-error** 
...
end note
receiver --> sender: Message acknowledgement
note right
MessageHeader.id: **0002**
MessageHeader.extension.
messageheader-response-request.
valueCode: **never**
MessageHeader.response.identifier: **0001**
MessageHeader.response.code: **transient-error**
OperationOutcome.issue.severity: **fatal**
OperationOutcome.issue.code: **exception**
...
end note
</plantuml> |
| 1.3.8 | System A sends a Message to System B where messageheader-response-request.value is 'on-error'. System B receives the Message but is unable to process it because an internal timeout on the server has occurred. System B response with a Message where MessageHeader.response.code is ‘transient-error’, OperationOutcome.issue.severity is ‘fatal’ and OperationOutcome.issue.code is ‘timeout’. | <plantuml>
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **on-error** 
...
end note
receiver --> sender: Message acknowledgement
note right
MessageHeader.id: **0002**
MessageHeader.extension.
messageheader-response-request.
valueCode: **never**
MessageHeader.response.identifier: **0001**
MessageHeader.response.code: **transient-error**
OperationOutcome.issue.severity: **fatal**
OperationOutcome.issue.code: **timeout**
...
end note
</plantuml> |
| 1.3.9 | System A sends a Message to System B where messageheader-response-request.value is 'on-error'. System B receives the Message but is unable to process it because some of the data sources could not be accessed within a suitable time. System B response with a Message where MessageHeader.response.code is ‘transient-error’, OperationOutcome.issue.severity is ‘fatal’ and OperationOutcome.issue.code is ‘incomplete’. | <plantuml>
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **on-error** 
...
end note
receiver --> sender: Message acknowledgement
note right
MessageHeader.id: **0002**
MessageHeader.extension.
messageheader-response-request.
valueCode: **never**
MessageHeader.response.identifier: **0001**
MessageHeader.response.code: **transient-error**
OperationOutcome.issue.severity: **fatal**
OperationOutcome.issue.code: **incomplete** 
...
end note
</plantuml> |
| 1.3.10 | System A sends a Message to System where messageheader-response-request.value is 'on-error'. System B receives the Message but is unable to attempt to process it due to the server at System B being throttled because of a suspected Denial of Service attack. System B responds with a Message where MessageHeader.response.code is 'transient-error', OperationOutcome.issue.severity is 'fatal', and OperationOutcome.issue.code is 'throttled'. | <plantuml>
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **on-error** 
...
end note
receiver --> sender: Message acknowledgement
note right
MessageHeader.id: **0002**
MessageHeader.extension.
messageheader-response-request.
valueCode: **never**
MessageHeader.response.identifier: **0001**
MessageHeader.response.code: **transient-error**
OperationOutcome.issue.severity: **fatal**
OperationOutcome.issue.code: **throttled**
...
end note
</plantuml> |
| 1.3.11 | System A sends a Message to System where messageheader-response-request.value is 'always'. System B receives the Message but identifies that the content of the Message is invalid against the FHIR specification or a profile. The invalid content issue is either not specifically known or does not fit with existing sub-error codes. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is 'invalid'. | <plantuml>
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **on-error** 
...
end note
receiver --> sender: Message acknowledgement
note right
MessageHeader.id: **0002**
MessageHeader.extension.
messageheader-response-request.
valueCode: **never**
MessageHeader.response.identifier: **0001**
MessageHeader.response.code: **fatal-error**
OperationOutcome.issue.severity: **fatal OR error**
OperationOutcome.issue.code: **invalid**
...
end note
</plantuml> |
| 1.3.12 | System A sends a Message to System where messageheader-response-request.value is 'always'. System B receives the Message but identifies that there is a structural issue within the Message. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is 'structure'. | <plantuml>
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **on-error** 
...
end note
receiver --> sender: Message acknowledgement
note right
MessageHeader.id: **0002**
MessageHeader.extension.
messageheader-response-request.
valueCode: **never**
MessageHeader.response.identifier: **0001**
MessageHeader.response.code: **fatal-error**
OperationOutcome.issue.severity: **fatal OR error**
OperationOutcome.issue.code: **structure**
...
end note
</plantuml> |
| 1.3.13 | System A sends a Message to System where messageheader-response-request.value is 'always'. System B receives the Message but identifies that a required element is missing within the Message. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is 'required'. | <plantuml>
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **on-error** 
...
end note
receiver --> sender: Message acknowledgement
note right
MessageHeader.id: **0002**
MessageHeader.extension.
messageheader-response-request.
valueCode: **never**
MessageHeader.response.identifier: **0001**
MessageHeader.response.code: **fatal-error**
OperationOutcome.issue.severity: **fatal OR error**
OperationOutcome.issue.code: **required**
...
end note
</plantuml> | 
| 1.3.14 | System A sends a Message to System where messageheader-response-request.value is 'always'. System B receives the Message but identifies that an element or header value is invalid within the Message. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is 'value'. | <plantuml>
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **on-error** 
...
end note
receiver --> sender: Message acknowledgement
note right
MessageHeader.id: **0002**
MessageHeader.extension.
messageheader-response-request.
valueCode: **never**
MessageHeader.response.identifier: **0001**
MessageHeader.response.code: **fatal-error**
OperationOutcome.issue.severity: **fatal OR error**
OperationOutcome.issue.code: **value**
...
end note
</plantuml> |
| 1.3.15 | System A sends a Message to System where messageheader-response-request.value is 'always'. System B receives the Message but identifies that a content validation rule failed against the content within the Message. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is 'invarient'. | <plantuml>
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **on-error** 
...
end note
receiver --> sender: Message acknowledgement
note right
MessageHeader.id: **0002**
MessageHeader.extension.
messageheader-response-request.
valueCode: **never**
MessageHeader.response.identifier: **0001**
MessageHeader.response.code: **fatal-error**
OperationOutcome.issue.severity: **fatal OR error**
OperationOutcome.issue.code: **invarient**
...
end note
</plantuml> |
| 1.3.16 | System A sends a Message to System where messageheader-response-request.value is 'always'. System B identifies that there is a security issue. The specific issue is either not known or does not fit with existing sub-error codes. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is 'security'. | <plantuml>
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **on-error** 
...
end note
receiver --> sender: Message acknowledgement
note right
MessageHeader.id: **0002**
MessageHeader.extension.
messageheader-response-request.
valueCode: **never**
MessageHeader.response.identifier: **0001**
MessageHeader.response.code: **fatal-error**
OperationOutcome.issue.severity: **fatal OR error**
OperationOutcome.issue.code: **security**
...
end note
</plantuml> |
| 1.3.17 | System A sends a Message to System where messageheader-response-request.value is 'always'. System B identifies that the client had not initiated an authentication process. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is 'login'. | <plantuml>
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **on-error** 
...
end note
receiver --> sender: Message acknowledgement
note right
MessageHeader.id: **0002**
MessageHeader.extension.
messageheader-response-request.
valueCode: **never**
MessageHeader.response.identifier: **0001**
MessageHeader.response.code: **fatal-error**
OperationOutcome.issue.severity: **fatal OR error**
OperationOutcome.issue.code: **login**
...
end note
</plantuml> |
| 1.3.18 | System A sends a Message to System where messageheader-response-request.value is 'always'. System B identifies that the user or system was unknown and not able to authenticate. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is 'unknown'. | <plantuml>
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **on-error** 
...
end note
receiver --> sender: Message acknowledgement
note right
MessageHeader.id: **0002**
MessageHeader.extension.
messageheader-response-request.
valueCode: **never**
MessageHeader.response.identifier: **0001**
MessageHeader.response.code: **fatal-error**
OperationOutcome.issue.severity: **fatal OR error**
OperationOutcome.issue.code: **unknown**
...
end note
</plantuml> |
| 1.3.19 | System A sends a Message to System where messageheader-response-request.value is 'always'. System B identifies that the user session has expired. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is 'expired'. | <plantuml>
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **on-error** 
...
end note
receiver --> sender: Message acknowledgement
note right
MessageHeader.id: **0002**
MessageHeader.extension.
messageheader-response-request.
valueCode: **never**
MessageHeader.response.identifier: **0001**
MessageHeader.response.code: **fatal-error**
OperationOutcome.issue.severity: **fatal OR error**
OperationOutcome.issue.code: **expired**
...
end note
</plantuml> |
| 1.3.20 | System A sends a Message to System where messageheader-response-request.value is 'always'. System B identifies that the user does not have the rights to perform the action. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is 'forbidden'. | <plantuml>
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **on-error** 
...
end note
receiver --> sender: Message acknowledgement
note right
MessageHeader.id: **0002**
MessageHeader.extension.
messageheader-response-request.
valueCode: **never**
MessageHeader.response.identifier: **0001**
MessageHeader.response.code: **fatal-error**
OperationOutcome.issue.severity: **fatal OR error**
OperationOutcome.issue.code: **forbidden**
...
end note
</plantuml> |
| 1.3.21 | System A sends a Message to System where messageheader-response-request.value is 'always'. System B identifies that some information cannot, or might not, be able to be retuned to System A due to business, consent, privacy, or access rules. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is 'suppressed'. | <plantuml>
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **on-error** 
...
end note
receiver --> sender: Message acknowledgement
note right
MessageHeader.id: **0002**
MessageHeader.extension.
messageheader-response-request.
valueCode: **never**
MessageHeader.response.identifier: **0001**
MessageHeader.response.code: **fatal-error**
OperationOutcome.issue.severity: **fatal OR error**
OperationOutcome.issue.code: **suppressed**
...
end note
</plantuml> |
| 1.3.22 | System A sends a Message to System where messageheader-response-request.value is 'always'. System B is unable to fully process the request. The specific reason is either unknown or does not fit with existing sub-error codes. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is 'processing'. | <plantuml>
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **on-error** 
...
end note
receiver --> sender: Message acknowledgement
note right
MessageHeader.id: **0002**
MessageHeader.extension.
messageheader-response-request.
valueCode: **never**
MessageHeader.response.identifier: **0001**
MessageHeader.response.code: **fatal-error**
OperationOutcome.issue.severity: **fatal OR error**
OperationOutcome.issue.code: **processing**
...
end note
</plantuml> |
| 1.3.23 | System A sends a Message to System where messageheader-response-request.value is 'always'. System B is unable to process the Message because an interaction, operation, resource, or profile is not supported. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is 'not-supported'. | <plantuml>
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **on-error** 
...
end note
receiver --> sender: Message acknowledgement
note right
MessageHeader.id: **0002**
MessageHeader.extension.
messageheader-response-request.
valueCode: **never**
MessageHeader.response.identifier: **0001**
MessageHeader.response.code: **fatal-error**
OperationOutcome.issue.severity: **fatal OR error**
OperationOutcome.issue.code: **not-supported**
...
end note
</plantuml> |
| 1.3.24 | System A sends a Message to System where messageheader-response-request.value is 'always'. System B is unable to process the Message because an attempt was made to duplicate a record. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is ‘duplicate’. | <plantuml>
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **on-error** 
...
end note
receiver --> sender: Message acknowledgement
note right
MessageHeader.id: **0002**
MessageHeader.extension.
messageheader-response-request.
valueCode: **never**
MessageHeader.response.identifier: **0001**
MessageHeader.response.code: **fatal-error**
OperationOutcome.issue.severity: **fatal OR error**
OperationOutcome.issue.code: **duplicate**
...
end note
</plantuml> | 
| 1.3.25 | System A sends a Message to System where messageheader-response-request.value is 'always'. System B is unable to process the Message because multiple matching records were found when the operation required only one match. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is ‘multiple-matches’. | <plantuml>
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **on-error** 
...
end note
receiver --> sender: Message acknowledgement
note right
MessageHeader.id: **0002**
MessageHeader.extension.
messageheader-response-request.
valueCode: **never**
MessageHeader.response.identifier: **0001**
MessageHeader.response.code: **fatal-error**
OperationOutcome.issue.severity: **fatal OR error**
OperationOutcome.issue.code: **multiple-matches**
...
end note
</plantuml> |
| 1.3.26 | System A sends a Message to System where messageheader-response-request.value is 'always'. System B is unable to process the Message because the reference provided was not found. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is ‘not-found’. | <plantuml>
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **on-error** 
...
end note
receiver --> sender: Message acknowledgement
note right
MessageHeader.id: **0002**
MessageHeader.extension.
messageheader-response-request.
valueCode: **never**
MessageHeader.response.identifier: **0001**
MessageHeader.response.code: **fatal-error**
OperationOutcome.issue.severity: **fatal OR error**
OperationOutcome.issue.code: **not-found**
...
end note
</plantuml> |
| 1.3.27 | System A sends a Message to System where messageheader-response-request.value is 'always'. System B is unable to process the Message because the reference pointed to content that has been deleted. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is ‘deleted’. | <plantuml>
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **on-error** 
...
end note
receiver --> sender: Message acknowledgement
note right
MessageHeader.id: **0002**
MessageHeader.extension.
messageheader-response-request.
valueCode: **never**
MessageHeader.response.identifier: **0001**
MessageHeader.response.code: **fatal-error**
OperationOutcome.issue.severity: **fatal OR error**
OperationOutcome.issue.code: **deleted**
...
end note
</plantuml> |
| 1.3.28 | System A sends a Message to System where messageheader-response-request.value is 'always'. System B is unable to process the Message because the provided content in the Message is too long. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is ‘too-long’. | <plantuml>
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **on-error** 
...
end note
receiver --> sender: Message acknowledgement
note right
MessageHeader.id: **0002**
MessageHeader.extension.
messageheader-response-request.
valueCode: **never**
MessageHeader.response.identifier: **0001**
MessageHeader.response.code: **fatal-error**
OperationOutcome.issue.severity: **fatal OR error**
OperationOutcome.issue.code: **too-long**
...
end note
</plantuml> |
| 1.3.29 | System A sends a Message to System where messageheader-response-request.value is 'always'. System B is unable to process the Message because there is an invalid code or system within the Message. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is ‘code-invalid’. | <plantuml>
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **on-error** 
...
end note
receiver --> sender: Message acknowledgement
note right
MessageHeader.id: **0002**
MessageHeader.extension.
messageheader-response-request.
valueCode: **never**
MessageHeader.response.identifier: **0001**
MessageHeader.response.code: **fatal-error**
OperationOutcome.issue.severity: **fatal OR error**
OperationOutcome.issue.code: **code-invalid**
...
end note
</plantuml> |
| 1.3.30 | System A sends a Message to System where messageheader-response-request.value is 'always'. System B is unable to process the Message because there is an unacceptable extension within the Message. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is ‘extension’. | <plantuml>
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **on-error** 
...
end note
receiver --> sender: Message acknowledgement
note right
MessageHeader.id: **0002**
MessageHeader.extension.
messageheader-response-request.
valueCode: **never**
MessageHeader.response.identifier: **0001**
MessageHeader.response.code: **fatal-error**
OperationOutcome.issue.severity: **fatal OR error**
OperationOutcome.issue.code: **extension**
...
end note
</plantuml> |
| 1.3.31 | System A sends a Message to System where messageheader-response-request.value is 'always'. System B is unable to process the Message because the operation was stopped to protect server resources. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is ‘too-costly’. |<plantuml>
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **on-error** 
...
end note
receiver --> sender: Message acknowledgement
note right
MessageHeader.id: **0002**
MessageHeader.extension.
messageheader-response-request.
valueCode: **never**
MessageHeader.response.identifier: **0001**
MessageHeader.response.code: **fatal-error**
OperationOutcome.issue.severity: **fatal OR error**
OperationOutcome.issue.code: **too-costly**
...
end note
</plantuml> |
| 1.3.32 | System A sends a Message to System where messageheader-response-request.value is 'always'. System B is unable to process the Message because there was a failure of a business rule. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is ‘business-rule’. | <plantuml>
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **on-error** 
...
end note
receiver --> sender: Message acknowledgement
note right
MessageHeader.id: **0002**
MessageHeader.extension.
messageheader-response-request.
valueCode: **never**
MessageHeader.response.identifier: **0001**
MessageHeader.response.code: **fatal-error**
OperationOutcome.issue.severity: **fatal OR error**
OperationOutcome.issue.code: **business-rule**
...
end note
</plantuml> |
| 1.3.33 | System A sends a Message to System where messageheader-response-request.value is 'always'. System B is unable to process the Message because there is an edit conflict. System B responds with a Message where MessageHeader.response.code is 'fatal-error', OperationOutcome.issue.severity is 'fatal' OR ‘error’, and OperationOutcome.issue.code is ‘conflict’. | <plantuml>
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **on-error** 
...
end note
receiver --> sender: Message acknowledgement
note right
MessageHeader.id: **0002**
MessageHeader.extension.
messageheader-response-request.
valueCode: **never**
MessageHeader.response.identifier: **0001**
MessageHeader.response.code: **fatal-error**
OperationOutcome.issue.severity: **fatal OR error**
OperationOutcome.issue.code: **conflict**
...
end note
</plantuml> |
| 1.4.1 | System A sends a Message to System where messageheader-response-request.value is 'never'. System B receives the Message and determines that the Message has no technical issues. However, System B does NOT send an acknowledgement. | <plantuml>
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **never** 
...
end note
</plantuml> |
| 1.4.2 | System A sends a Message to System where messageheader-response-request.value is 'never'. System B receives the Message but there is a technical issue where a mandatory element is missing. However, System B does NOT send an acknowledgement. | <plantuml>
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **never** 
...
end note
</plantuml> |
| 1.4.3 | System A sends a Message to System where messageheader-response-request.value is 'never'. System B receives the Message but there is an unexpected internal error on the server. However, System B does NOT send an acknowledgement. | <plantuml>
participant "System A" as sender
participant "System B" as receiver
sender -> receiver: Message request
note left
MessageHeader.id: **0001**
MessageHeader.extension.
messageheader-response-request.
valueCode: **never** 
...
end note
</plantuml> |





