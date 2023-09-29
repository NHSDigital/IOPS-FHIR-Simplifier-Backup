#### Post Alert

The SCR API provides a create operation, Post Alert, to allow GP Systems to record TMS Event Service (TES) Alerts centrally.


| Endpoint |
|--|
| https://[baseURL]/AuditEvent |


| Query |
|--|
| POST https://[baseUrl]/AuditEvent |

| Payload |
|--|
| {{pagelink:scr-alert-auditevent}} |


### Post Alert sequence diagram

{{render:auditevent}}

### Example Post Alert call


```
POST https://[baseUrl]/AuditEvent /HTTP/1
```

### Example Post Alert call payload

{{json:auditevent-example}}

### Example Post Alert success response

Returns a minimal response, i.e. just the successful http status, on successful write to the repository.

```
HTTP/1.1 201 Created
Date: Tue, 24 Aug 2020 11:00:00 GMT
Content-Type: application/fhir+json
```



### Example Post Alert failure response

Returns an operationOutcome on failure. Error handling is in line with <a href="https://nhsd-confluence.digital.nhs.uk/display/APM/2020-04-17+Spine+Error+Codes+II">Spine Error Codes II</a> [NB: internal Confluence link].

```
HTTP/1.1 400 Bad Request
Date: Tue, 24 Aug 2020 11:00:00 GMT
Content-Type: application/fhir+json
```

```json
{
  "resourceType": "OperationOutcome",
  "id": "27242108-f2ee-429c-a387-ace44bb87f40",
  "issue": [
    {
      "severity": "error",
      "code": "invalid",
      "details": {
        "text": "Bad Request"
      }
    }
  ]
}