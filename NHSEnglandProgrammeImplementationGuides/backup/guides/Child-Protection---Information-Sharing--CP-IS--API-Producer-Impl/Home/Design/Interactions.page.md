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

| Outcome         | Response                       |
| ----------- | ------------------------  |
| Record found       | <a href="https://simplifier.net/guide/child-protection---information-sharing--cp-is--api-producer-impl/home/examples/use-case---get-careteam.page.md?version=current#success-case">SearchSet Bundle</a> |
| No record found       | <a href="https://simplifier.net/guide/child-protection---information-sharing--cp-is--api-producer-impl/home/examples/use-case---get-careteam.page.md?version=current#no-record-found-case">SearchSet Bundle</a> |
| Error or validation failure      | OperationOutcome - {{pagelink:Home/Build/Errorhandling.page.md}}|

<br>

### Query for AuditEvent information

**Http query**

**<font color="#00008B">GET</font>** /AuditEvent?patient:identifier=https://fhir.nhs.uk/Id/nhs-number|[nhs-number]&_include=AuditEvent:entity-type=http://terminology.hl7.org/CodeSystem/v3-RoleClass|ASSIGNED

**Parameters**

The patient's NHS Number. This must be a verified NHS Number.
- patient:identifier (required), type <a href='http://hl7.org/fhir/R4/search.html#token'>token</a>. 

<br>

**Headers**

- Authorization: Bearer [access token]
- TraceID: [yourRef]
- IsUnscheduledAccessEvent: [boolean]

**Conformance**

The Producer API SHALL return Access History information formatted as an AuditEvent resource with an included PractitionerRole resource, as per the {{pagelink:Home/Design/Data-mapping.page.md}}, in conformance with idiomatic restful [FHIR search-with-includes](http://hl7.org/fhir/r4/search.html#revinclude) pattern.

<br>
{{render:cpis-get-auditevent-producer}}

<br>

| Outcome         | Response                       |
| ----------- | ------------------------  |
| Record found       | <a href="https://simplifier.net/guide/child-protection---information-sharing--cp-is--api-producer-impl/home/examples/use-case---get-auditevent.page.md?version=current#success-case">SearchSet Bundle</a> |
| No record found       | <a href="https://simplifier.net/guide/child-protection---information-sharing--cp-is--api-producer-impl/home/examples/use-case---get-auditevent.page.md?version=current#no-record-found-case">SearchSet Bundle</a> |
| Error or validation failure      | OperationOutcome - {{pagelink:Home/Build/Errorhandling.page.md}} |
