## {{page-title}}

When the Spine Secure Proxy cannot or will not process a request then one of the following errors are used to return debug details:

<table class="nhsd-!t-margin-bottom-6">
  <thead>
    <tr>
      <th data-no-sort>HTTP code</th>
      <th data-no-sort>Issue type</th>
      <th data-no-sort>Description of error</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>400</code></td>
      <td>invalid</td>
      <td>Target URL varies from endpoint registered in SDS</td>
    </tr>
    <tr>
      <td><code>403</code></td>
      <td>forbidden</td>
      <td>Sender ASID is not authorised for this interaction</td>
    </tr>
    <tr>
      <td><code>403</code></td>
      <td>forbidden</td>
      <td>Receiver ASID is not authorised for this interaction</td>
    </tr>
    <tr>
      <td><code>403</code></td>
      <td>forbidden</td>
      <td>Sender ASID is not authorised to send the interaction to receiver ASID</td>
    </tr>
    <tr>
      <td><code>405</code></td>
      <td>not-supported</td>
      <td>Method not allowed</td>
    </tr>
    <tr>
      <td><code>415</code></td>
      <td>not-supported</td>
      <td>Unsupported media type</td>
    </tr>
    <tr>
      <td><code>502</code></td>
      <td>transient</td>
      <td>Error communicating to target URL</td>
    </tr>
  </tbody>
</table>

### SSP error example: Target URL varies from endpoint registered in SDS

```xml
{
    "resourceType": "OperationOutcome", 
    "id": "09a01679-2564-0fb4-5129-aecc81ea2706",
    "issue": [
        {
            "code": "invalid", 
            "severity": "error", 
            "details": {
                "coding": [
                    {
                        "code": "400", 
                        "display": "ENDPOINT_https://supplier.thirdparty.nhs.uk/v1/fhir/_CPAID_S000000000001_VARIES_FROM_TARGETURL_https://supplier.thirdparty.nhs.uk/v1/test", 
                        "system": "http://fhir.nhs.net/ValueSet/gpconnect-schedule-response-code-1-0"
                    }
                ]
            },
            "diagnostics": "ENDPOINT_https://supplier.thirdparty.nhs.uk/v1/fhir/_CPAID_S000000000001_VARIES_FROM_TARGETURL_https://supplier.thirdparty.nhs.uk/v1/test",
        }
    ] 
}
```

### SSP error example: Sender ASID is not authorised for this interaction

```xml
{
    "resourceType": "OperationOutcome",
    "id": "10960df2-29d1-4e71-823c-c0bb9d723012",
    "issue": [
        {
            "code": "forbidden",
            "severity": "error",
            "details": {
                "coding": [
                    {
                        "code": "403",
                        "display": "ASID_CHECK_FAILED_MESSAGESENDER_100000000001",
                        "system": "http://fhir.nhs.net/ValueSet/gpconnect-schedule-response-code-1-0"
                    }
                ]
            },
            "diagnostics": "ASID_CHECK_FAILED_MESSAGESENDER_100000000001"
        }
    ]
}
```

### SSP error example: Receiver ASID is not authorised for this interaction

```xml
{
    "resourceType": "OperationOutcome",
    "id": "018C2550-358F-4F68-BE19-88C80A859E0A",
    "issue": [
        {
            "code": "forbidden",
            "severity": "error",
            "details": {
                "coding": [
                    {
                        "code": "403",
                        "display": "PARTYKEY_INTERACTION_CHECK_FAILED_MESSAGERECEIVER_200000000002",
                        "system": "http://fhir.nhs.net/ValueSet/gpconnect-schedule-response-code-1-0"
                    }
                ]
            },
            "diagnostics": "PARTYKEY_INTERACTION_CHECK_FAILED_MESSAGERECEIVER_200000000002"
        }
    ]
}
```

### SSP error example: Sender ASID is not authorised to send the interaction to receiver ASID

```xml
{
    "resourceType": "OperationOutcome",
    "id": "43A8BB0D-195E-4CF4-86F9-E8514F6EB585",
    "issue": [
        {
            "code": "forbidden",
            "severity": "error",
            "details": {
                "coding": [
                    {
                        "code": "403",
                        "display": "FOT_CHECK_FAILED_MESSAGESENDER_200000000001_MESSAGERECEIVER_200000000002",
                        "system": "http://fhir.nhs.net/ValueSet/gpconnect-schedule-response-code-1-0"
                    }
                ]
            },
            "diagnostics": "FOT_CHECK_FAILED_MESSAGESENDER_200000000001_MESSAGERECEIVER_200000000002"
        }
    ]
}
```

### SSP error example: Method not allowed

```xml
{
  "resourceType": "OperationOutcome",
  "issue": [
    {
      "code": "forbidden",
      "severity": "fatal",
      "details": {
        "coding": [
          {
            "code": "405",
            "system": "https://fhir.nhs.uk/StructureDefinition/spine-operationoutcome-1",
            "display": "405: Method Not Allowed"
          }
        ]
      }
    }
  ]
}
```

### SSP error example: Unsupported media type

```xml
{
  "resourceType": "OperationOutcome",
  "id": "09a01679-2564-0fb4-5129-aecc81ea2706",
  "issue": [
    {
      "code": "not-supported",
      "severity": "error",
      "details": {
        "coding": [
          {
            "code": "415",
            "display": "Unsupported_Media_Type",
            "system": "http://fhir.nhs.net/ValueSet/gpconnect-schedule-response-code-1-0"
          }
        ]
      },
      "diagnostics": "Unsupported_Media_Type"
    }
  ]
}
```

### SSP error example: Error communicating to target URL

```xml
{
  "resourceType": "OperationOutcome",
  "id": "78D536C0-44D6-11E9-BFCD-17C1B88243CD",
  "issue": [
    {
      "code": "transient",
      "severity": "error",
      "details": {
        "coding": [
          {
            "display": "ERROR_COMMUNICATING_TO_ENDPOINT_URL_https://supplier.thirdparty.nhs.uk/D11111/STU3/1/GPConnect/Patient",
            "code": "502",
            "system": "http://fhir.nhs.net/ValueSet/gpconnect-schedule-response-code-1-0"
          }
        ]
      },
      "diagnostics": "ERROR_COMMUNICATING_TO_ENDPOINT_URL_https://supplier.thirdparty.nhs.uk/D11111/STU3/1/GPConnect/Patient"
    }
  ]
}
```