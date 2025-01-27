## {{page-title}}

On receiving the request, the GP system should respond back to the national proxy service with either an `accepted` or `rejected`. In the example below, the `status` has been changed to `accepted`. For a rejected example see {{pagelink:Home/FHIR-Assets/Examples/Task-Consent-Verification-Rejected.page.md}} where the status is now `rejected` and a note has been added to indicate the rejection reason (e.g. patient not registered).



 ```
PUT https://proxyservice.example.nhs.uk/FHIR/R4/Task?identifier={identifier}
```

### Event Payload Example

{{pagelink:Home/FHIR-Assets/Examples/Task-Consent-Verification-Accepted.page.md}}