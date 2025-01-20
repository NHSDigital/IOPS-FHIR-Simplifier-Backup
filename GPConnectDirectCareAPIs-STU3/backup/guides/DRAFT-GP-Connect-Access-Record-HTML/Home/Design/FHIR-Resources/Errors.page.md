## {{page-title}}

If there is a problem with the request or an error occurs during processing of the request then the provider should return an HTTP error along with an “OperationOutcome” resource within the response payload. Details of the required error responses are available on the {{pagelink:Home/Design/Error-handling-guidance}} page.

### Response

- [gpconnect-operationoutcome-1](https://data.developer.nhs.uk/fhir/candidaterelease-170816-getrecord/Profile.GetRecordQueryResponse-HTMLView/gpconnect-operationoutcome-1.html) (based on [FHIR OperationOutcome](https://www.hl7.org/fhir/DSTU2/operationoutcome.html))