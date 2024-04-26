## {{page-title}}

### UKCoreMessageEvent

<div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b> Important:</b> The Acknowledgement Framework is currently a draft version. Please contact the <a href="mailto:interoperabilityteam@nhs.net?subject=Acknowledgement Framework">Interoperability Standards Team</a> if you are interested to discuss this solution for your use case.</div>

Scope: Profile MessageHeader

{{render:https://fhir.hl7.org.uk/CodeSystem/UKCore-MessageEvent}}

**Note:** This CodeSystem is currently retired. A discussion will need to take place as to how this CodeSystem can be used and what values should be added, as well as its retired status and visibility in UK Core.

In the meantime, the codes in the CodeSystem can be accessed directly by clicking <a href="https://simplifier.net/hl7fhirukcorer4/codesystem-ukcore-messageevent">here</a>.

Below are the codes in the CodeSystem that existed as of 20/01/2023.

| Code | System | Display |
| ---- | ------ | ------- |
| appointment | https://fhir.nhs.uk/CodeSystem/message-event | Appointment |
| dispense-notification | https://fhir.nhs.uk/CodeSystem/message-event | Dispense Notification |
| dispense-notification-update | https://fhir.nhs.uk/CodeSystem/message-event | Dispense Notification Update |
| document | https://fhir.nhs.uk/CodeSystem/message-event | Document |
| document-notification | https://fhir.nhs.uk/CodeSystem/message-event | Document Notification |
| notification | https://fhir.nhs.uk/CodeSystem/message-event | Event Notification |
| patient | https://fhir.nhs.uk/CodeSystem/message-event | Patient Demographics |
| encounter | https://fhir.nhs.uk/CodeSystem/message-event | Patient Encounter |
| referral | https://fhir.nhs.uk/CodeSystem/message-event | Patient Referral |
| patient-notification | https://fhir.nhs.uk/CodeSystem/message-event | Patient Notifications |
| prescription-order | https://fhir.nhs.uk/CodeSystem/message-event | Prescription Order |
| prescription-order-response | https://fhir.nhs.uk/CodeSystem/message-event | Prescription Order Response |
| prescription-order-update | https://fhir.nhs.uk/CodeSystem/message-event | Prescription Order Update |
| unsolicited-action | https://fhir.nhs.uk/CodeSystem/message-event | Unsolicited actions |
| unsolicited-observations | https://fhir.nhs.uk/CodeSystem/message-event | Unsolicited Observations |
| vaccinations | https://fhir.nhs.uk/CodeSystem/message-event | Vaccinations |
| booking-request | https://fhir.nhs.uk/CodeSystem/message-events-bars | Booking Request - Request |
| booking-response | https://fhir.nhs.uk/CodeSystem/message-events-bars | Booking Request - Response |
| servicerequest-request | https://fhir.nhs.uk/CodeSystem/message-events-bars | Service Request - Request |
| servicerequest-response | https://fhir.nhs.uk/CodeSystem/message-events-bars | Service Request - Response |

### ExampleMessageReasonCodes

Scope: Profile MessageHeader

**Note:** This is an Example binding in MessageHeader.reason and so there will need to be a further discussion about whether any changes or codes should be added to this CodeSystem in the future.

{{render:http://terminology.hl7.org/CodeSystem/message-reasons-encounter}}

### ResponseType

Scope: Profile MessageHeader

{{render:http://hl7.org/fhir/response-code}}

### IssueSeverity

Scope: Profile OperationOutcome

{{render:http://hl7.org/fhir/issue-severity}}

### IssueType

Scope: Profile OperationOutcome

{{render:http://hl7.org/fhir/issue-type}}

### AcknowledgementFrameworkResponseCode

Scope: Profile OperationOutcome

This CodeSystem includes the majority of codes from CodeSystem http://terminology.hl7.org/CodeSystem/operation-outcome in the HL7 International base standard. In addition, additional codes have been added which are displayed in bold at the bottom of the list.

The System URL has yet to be determined and the CodeSystem file will also need to be created.

| Code | Display |
| - | ------------------- |
| DELETE_MULTIPLE_MATCHES | Error: Multiple matches exist for the conditional delete |
| MSG_AUTH_REQUIRED | You must authenticate before you can use this service |
| MSG_BAD_FORMAT | Bad Syntax: "%s" must be a %s' |
| MSG_BAD_SYNTAX | Bad Syntax in %s |
| MSG_CANT_PARSE_CONTENT | Unable to parse feed (entry content type = "%s") |
| MSG_CANT_PARSE_ROOT | Unable to parse feed (root element name = "%s") |
| MSG_CREATED | New resource created |
| MSG_DATE_FORMAT | The Date value %s is not in the correct format (Xml Date Format required) |
| MSG_DELETED | This resource has been deleted |
| MSG_DELETED_DONE | Resource deleted |
| MSG_DELETED_ID | The resource "%s" has been deleted |
| MSG_DUPLICATE_ID | Duplicate Id %s for resource type %s |
| MSG_ERROR_PARSING | Error parsing resource Xml (%s) |
| MSG_ID_INVALID | Id "%s" has an invalid character "%s" |
| MSG_ID_TOO_LONG | Id "%s" too long (length limit 36) |
| MSG_INVALID_ID | Id not accepted |
| MSG_JSON_OBJECT | Json Source for a resource should start with an object |
| MSG_LOCAL_FAIL | Unable to resolve local reference to resource %s |
| MSG_NO_EXIST | Resource Id "%s" does not exist |
| MSG_NO_MATCH | No Resource found matching the query "%s" |
| MSG_NO_MODULE | No module could be found to handle the request "%s" |
| MSG_NO_SUMMARY | No Summary for this resource |
| MSG_OP_NOT_ALLOWED | Operation %s not allowed for resource %s (due to local configuration) |
| MSG_PARAM_CHAINED | Unknown chained parameter name "%s" |
| MSG_PARAM_INVALID | Parameter "%s" content is invalid |
| MSG_PARAM_MODIFIER_INVALID | Parameter "%s" modifier is invalid |
| MSG_PARAM_NO_REPEAT | Parameter "%s" is not allowed to repeat |
| MSG_PARAM_UNKNOWN | Parameter "%s" not understood |
| MSG_RESOURCE_EXAMPLE_PROTECTED | Resources with identity "example" cannot be deleted (for testing/training purposes) |
| MSG_RESOURCE_ID_FAIL | Unable to allocate resource id |
| MSG_RESOURCE_ID_MISMATCH | Resource Id Mismatch |
| MSG_RESOURCE_ID_MISSING | Resource Id Missing |
| MSG_RESOURCE_NOT_ALLOWED | Not allowed to submit a resource for this operation |
| MSG_RESOURCE_REQUIRED | A resource is required |
| MSG_RESOURCE_TYPE_MISMATCH | Resource Type Mismatch |
| MSG_SORT_UNKNOWN | Unknown sort parameter name "%s" |
| MSG_TRANSACTION_DUPLICATE_ID | Duplicate Identifier in transaction: %s |
| MSG_TRANSACTION_MISSING_ID | Missing Identifier in transaction - an entry.id must be provided |
| MSG_UNHANDLED_NODE_TYPE | Unhandled xml node type "%s" |
| MSG_UNKNOWN_CONTENT | Unknown Content (%s) at %s |
| MSG_UNKNOWN_OPERATION | Unknown FHIR http operation |
| MSG_UNKNOWN_TYPE | Resource Type "%s" not recognised |
| MSG_UPDATED | Existing resource updated |
| MSG_VERSION_AWARE | Version aware updates are required for this resource |
| MSG_VERSION_AWARE_CONFLICT | Update Conflict (server current version = "%s", client version referenced = "%s") |
| MSG_VERSION_AWARE_URL | Version specific URL not recognised |
| MSG_WRONG_NS | This does not appear to be a FHIR element or resource (wrong namespace "%s") |
| SEARCH_MULTIPLE | Error: Multiple matches exist for %s search parameters "%s" |
| SEARCH_NONE | Error: no processable search found for %s search parameters "%s" |
| UPDATE_MULTIPLE_MATCHES | Error: Multiple matches exist for the conditional update |

<br />

**Propose the following to be added to CodeSystem operation-outcome:**

| Code | Display | Definition |
| ---- | ------- | ---------- |
| **UNRECOGNISED_RECIPIENT** | Recipient is not recognised | Recipient is not recognised |
| **UNRECOGNISED_SENDER** | Sender is not recognised | Sender is not recognised |
| **NOT_APPROVED_ATTACHMENT_FILE_TYPE** | Attachment file type is not approved | Attachment file type is not approved |
| **UNSUPPORTED_ATTACHMENT_FILE_TYPE** | Attachment file type is not supported | Attachment file type is not supported |
| **DUPLICATE_BUNDLE_ID** | Bundle id is a duplicate | Bundle id is a duplicate |
| **EXCESSIVE_SIZE** | Payload size is too large | Payload size is too large |
| **TECHNICAL_SUCCESS** | Request successfully received | Request successfully received and no technical issues were identified |
| **BUSINESS_SUCCESS** | Business request successfully actioned | A person has successfully actioned the request. |
| **BUSINESS_FAIL** | Busines request not actioned | A person has declined to action the request. |
| **BUSINESS_FAIL_DATA_INAPPROPRIATE** | Data is inappropriate | The data makes no sense, dubious, contradictory, using foreign language, or other similar issues. |
| **BUSINESS_FAIL_RECIPIENT_INAPPROPRIATE** | Recipient is inappropriate | The recipient of the request cannot, or should not, action the request. |
| **BUSINESS_FAIL_SENDER_INAPPROPRIATE** | Sender is inappropriate | The sender of the request should not have sent the request (e.g. missing relevant qualifications). |
| **BUSINESS_FAIL_ALREADY_EXISTS** | Not added or registered because already exists | The specified person, entity, process, or other similar concept, cannot be added or registered because they/it already exists on the system. |
| **BUSINESS_FAIL_MAX_CAPACITY** | System has reached maximum capacity | The specified person, entity, process, or other similar concept, cannot be added or registered because the system has reached its maximum capacity. |
| **BUSINESS_FAIL_NOT_ALLOWED** | Not added or registered because is not allowed | The specified person, entity, process, or other similar concept, is not allowed to be added or registered (e.g. a patient is banned). |
| **PATIENT_KNOWN** | Patient is known and registered at this clinical setting | Patient is known and registered at this clinical setting |
| **PATIENT_NOT_KNOWN** | Patient is not known or registered at this clinical setting | Patient is not known or registered at this clinical setting |
| **PATIENT_PREVIOUSLY_KNOWN** | Patient is no longer at this clinical setting | Patient is no longer at this clinical setting |
| **PATIENT_KNOWN_AND_DECEASED** | Patient is known at this clinical setting but has recently deceased | Patient is known at this clinical setting but has recently deceased |

### messageheader-response-request

Scope: Extension messageheader-response-request

{{render:http://hl7.org/fhir/messageheader-response-request}}

