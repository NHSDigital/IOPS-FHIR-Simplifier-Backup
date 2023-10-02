## {{page-title}}

The CP-IS FHIR R4 API allows healthcare professionals to use healthcare applications acting as API consumers to search for, read and display CP-IS information.

The CP-IS FHIR R4 API provides 2 endpoints:

    - /CareTeam
    - /AuditEvent

which are searched and retrieved via http GET and a patient NHS Number searchParameter. So:

### Query for CP-IS information

**Http query**

**<font color="#00008B">GET</font>** /CareTeam?patient:identifier=https://fhir.nhs.uk/Id/nhs-number|[nhs-number];

**Parameters**

The patient's NHS Number. This must be a verified NHS Number.
- patient:identifier (required), type <a href='http://hl7.org/fhir/R4/search.html#token'>token</a>. 

<br>

**Headers**

- Authorization: Bearer [access token]
- TraceID: [yourRef]
- IsUnscheduledAccessEvent: [boolean]

<br>
{{render:cpis-get-careteam-producer}}
<br>
<br>

| Outcome         | Response                       |
| ----------- | ------------------------  |
| Record found       | SearchSet Bundle - {{pagelink:Home/Examples/Example-found.page.md}}|
| No record found       | SearchSet Bundle - {{pagelink:Home/Examples/Example-not-found.page.md}}|
| Error or validation failure      | OperationOutcome - {{pagelink:Home/Build/Errorhandling.page.md}}|

<br>

### Query for AuditEvent information

**Http query **

**<font color="#00008B">GET</font>** /AuditEvent?patient:identifier=https://fhir.nhs.uk/Id/nhs-number|[nhs-number]

**Parameters**

The patient's NHS Number. This must be a verified NHS Number.
- patient:identifier (required), type <a href='http://hl7.org/fhir/R4/search.html#token'>token</a>. 

<br>

**Headers**

- Authorization: Bearer [access token]
- TraceID: [yourRef]
- IsUnscheduledAccessEvent: [boolean]



<br>
{{render:cpis-get-auditevent-producer}}
<br>
<br>

| Outcome         | Response                       |
| ----------- | ------------------------  |
| Record found       | SearchSet Bundle - {{pagelink:Home/Examples/Example-found.page.md}}|
| No record found       | SearchSet Bundle - {{pagelink:Home/Examples/Example-not-found.page.md}}|
| Error or validation failure      | OperationOutcome - {{pagelink:Home/Build/Errorhandling.page.md}}|

<br>