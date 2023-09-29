#### Set Permission

The SCR API provides a custom operation, setPermission, to allow update of Permission to view for GP Summaries held for the patient. Possible values are Yes, No, Ask.

setPermission is specified in the OperationDefinition {{pagelink:setpermission-duplicate-3}}

| Endpoint |
|--|
| https://[baseURL]/$setPermission |



| Parameters |
|--|
| patient: NHSNo | |
| Permission value: Yes \| No \| Ask | Using coded values from CodeSystem {{pagelink:codesystem-scr-acspermission}} |

| Query |
|--|
| POST https://[baseUrl]/$setPermission |


### Client view of Get SCR Id sequence diagram

{{render:setPermission-duplicate-2}}

### Example setPermission call


```
POST https://[baseUrl]/$setPermission /HTTP/1
```

### Example setPermission call payload

setPermission passes in-parameter arguments as a Parameter payload

```json
{
    "resourceType": "Parameters",
    "parameter":  [
        {
            "name": "setPermissions",
            "part":  [
                {
                    "name": "nhsNumber",
                    "valueString": "999999998"
                },
                {
                    "name": "permissionCode",
                    "valueCoding": {
                        "system": "https://fhir.nhs.uk/CodeSystem/SCR-ACSPermission",
                        "code": "Ask"
                    }
                }
            ]
        }
    ]
}
```




### Example setPermission success response

Returns an operationOutcome on sucess or failure

```
HTTP/1.1 201 Created
Date: Tue, 24 Aug 2020 11:00:00 GMT
Content-Type: application/fhir+json
```

```json
{
  "resourceType": "OperationOutcome",
  "id": "27242108-f2ee-429c-a387-ace44bb87f40",
  "issue": [
    {
      "severity": "information",
      "code": "informational",
      "details": {
        "text": "Resource Created"
      }
    }
  ]
}
```


### Example setPermission failure response

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
```