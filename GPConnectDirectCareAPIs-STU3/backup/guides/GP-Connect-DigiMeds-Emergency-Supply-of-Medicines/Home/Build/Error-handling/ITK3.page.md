## {{page-title}}

- where the received message does not conform to the requirements stated for ITK3 header, or for the payload, the message **MUST** be considered invalid

- where a received message is invalid, an ITK3 Response **MUST** be generated with the corresponding Negative ITK3 Response Code, which indicates the nature of the error, and the message **MUST NOT** be accepted for downstream processing

More information on the response codes can be found in the article below:

- [Pragmatic use of ITK3 response codes for generic FHIR receive programmes](https://digital.nhs.uk/services/interoperability-toolkit/developer-resources/itk-test-centre/pragmatic-use-of-itk3-response-codes-for-generic-fhir-receive-programmes)

---