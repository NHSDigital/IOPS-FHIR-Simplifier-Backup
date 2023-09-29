## {{page-title}}

This page collates and summarises http headers to be included with http requests and responses submitted.

It is recommended that developers are familiar with the <a href='https://digital.nhs.uk/services/api-platform'>NHS England API Platform</a> which will provide the necessary <a href='https://digital.nhs.uk/developer/guides-and-documentation/security-and-authorisation#top'>Security, Authentication and Authorisation</a>.

### Requests

- Authorization: Bearer [access token]
- TraceID: [yourRef]

It is recommended that developers provide a unique reference number or identifier for the TraceID header for tracing purposes. UUID recommended.

### Responses

Responses will be provided with metadata headers
- Date: [servedDateTime]
- Content-type: application/fhir+json
