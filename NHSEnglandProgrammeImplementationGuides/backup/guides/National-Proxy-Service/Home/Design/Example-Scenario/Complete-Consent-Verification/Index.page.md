## {{page-title}}

After the request has been accepted, the request should be actioned. Once actioned the decision should should be sent back to the National Proxy with a status of `completed`. The decision is sent in the `output` element.



 ```
  PUT https://proxyservice.example.nhs.uk/FHIR/R4/Task?identifier={identifier}
```

### Event Payload Example

{{pagelink:Home/FHIR-Assets/Examples/Task-Consent-Verification-Completed.page.md}}