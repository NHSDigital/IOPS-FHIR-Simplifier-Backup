## {{page-title}}


A clinician treating a child submits a query to CP-IS to see child protection information access history. The querying clinician is a registered "smartcard" user.

The system issues a GET call to CP-IS for the child's NHS Number.

#### Get call

    GET [base]/AuditEvent?patient:identifier=https://fhir.nhs.uk/Id/nhs-number|[nhs-number]

#### Headers

    Authorization: Bearer Z2NVIitD7bQOzsoCpO3P
    TraceID: b2acfb2c-c40e-4f9a-8916-950a2e86fc4e
    IsUnscheduledAccessEvent: true

#### Payload

    None

### Success case

The system responds with a SearchSet Bundle containing the AuditEvent history information for previous accesses (upto 25).

#### Http response

    HTTP/1.1 200 OK

#### Headers

    Date: Tue, 05 Sep 2023 11:23:45 GMT
    Content-Type: application/fhir+json

#### Payload

<div class="tab">
  <button class="tablinks active" onclick="openTab(event, 'JSON')">JSON</button>
</div>
<div id="JSON" class="tabcontent" style="display:block">
{{json:145b0aa0-8709-4272-b7c0-75738a9822f3}}
</div>
