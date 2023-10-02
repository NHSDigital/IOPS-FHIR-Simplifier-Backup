## {{page-title}}

This page collates and summarises http headers to be included with http requests and responses submitted.

It is recommended that developers are familiar with and refer to technical documentation <a href='https://developer.nhs.uk/apis/spine-core/index.html' class='external'>Introduction to Spine Core FHIR API Framework</a> while integrating with any Spine systems.

### Requests

- Authorization: Bearer [access token]
- TraceID: [yourRef]
- IsUnscheduledAccessEvent: [boolean]

It is recommended that developers provide a unique reference number or identifier for the TraceID header for tracing purposes. UUID recommended.

### Responses

Responses will be provided with metadata headers
- Date: [servedDateTime]
- Content-type: application/fhir+json

## Custom header for CP-IS - IsUnscheduledAccessEvent

CP-IS distinguishes between Scheduled and Unscheduled care settings and/or episodes. These statuses are self-reported by the calling system. In the CP-IS FHIR R4 API this SHOULD be passed as a custom http header, IsUnscheduledEvent.

- When set to "true" the CP-IS Query originated from unscheduled care
- When set to "false" the CP-IS Query originated from scheduled care
- If the IsUnscheduledAccessEvent is omitted, it is assumed that the CP-IS Query originated from unscheduled care.

- When CP-IS Producer API receives an Unscheduled access, details of the access event, who, when, role, organisation, SHALL be added to the Access History.
- When CP-IS Producer API receives an Scheduled access, details of the access event, who, when, role, organisation, SHALL NOT be added to the Access History.