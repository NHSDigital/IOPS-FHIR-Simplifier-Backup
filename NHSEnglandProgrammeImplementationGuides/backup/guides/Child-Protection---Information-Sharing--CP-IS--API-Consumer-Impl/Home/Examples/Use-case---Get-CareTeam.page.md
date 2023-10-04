## {{page-title}}

A clinician treating a child submits a query to CP-IS to see if any child protection information exists. The querying clinician is a registered "smartcard" user. The care episode is unscheduled.

The system issues a GET call to CP-IS for the child's NHS Number.

#### Get call

    GET [base]/CareTeam?patient:identifier=https://fhir.nhs.uk/Id/nhs-number|[nhs-number]

#### Headers

    Authorization: Bearer Z2NVIitD7bQOzsoCpO3P
    TraceID: 6ede3b9d-a81b-4c75-9d77-e1d64d85c323
    IsUnscheduledAccessEvent: true

#### Payload

    None

### Success case
<a id="success-case"></a>

The system responds with a SearchSet Bundle containing the CareTeam responsible for the Care Plan, Period, and Contact information.

#### Http response

    HTTP/1.1 200 OK

#### Headers

    Date: Tue, 05 Sep 2023 11:23:34 GMT
    Content-Type: application/fhir+json

#### Payload

<div class="tab">
  <button class="tablinks active" onclick="openTab(event, 'JSON')">JSON</button>
</div>
<div id="JSON" class="tabcontent" style="display:block">
{{json:9daf8ceb-46eb-4314-9c6f-6900571a7dfa}}
</div>

### No record found case
<a id="no-record-found-case"></a>

The system responds with a 0 total record SearchSet Bundle.

#### Http response

    HTTP/1.1 200 OK

#### Headers

    Date: Tue, 05 Sep 2023 11:23:34 GMT
    Content-Type: application/fhir+json

#### Payload

<div class="tab">
  <button class="tablinks active" onclick="openTab(event, 'JSON')">JSON</button>
</div>
<div id="JSON" class="tabcontent" style="display:block">
{{json:7eb1bc82-da03-427b-b2d3-237bd6038cb7}}
</div>

### Error / Fail condition
<a id="error-case"></a>

The system responds with an OperationOutcome.

#### Http response

    HTTP/1.1 400 Bad Request

#### Headers

    Date: Tue, 05 Sep 2023 11:23:34 GMT
    Content-Type: application/fhir+json

#### Payload

<div class="tab">
  <button class="tablinks active" onclick="openTab(event, 'JSON')">JSON</button>
</div>
<div id="JSON" class="tabcontent" style="display:block">
{{json:57073625-1428-49e7-9ac5-abf1910cc58b}}
</div>
