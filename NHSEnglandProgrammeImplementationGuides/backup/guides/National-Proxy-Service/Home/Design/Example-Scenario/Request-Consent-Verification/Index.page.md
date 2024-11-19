## {{page-title}}

Once the proxy request has been processed, the patients GP can be asked to verify the relationship and proxy access request. In the FHIR Task the status is `requested`, asking for consent in the `code` element.A reference to the original request is supplied in the `focus` element, this can be used to retrieve the original request (the FHIR QuestionnaireResponse). 

The request starts a series of interactions following a [conversation pattern](https://www.enterpriseintegrationpatterns.com/patterns/conversation/index.html) where the national proxy service and primary care exchange FHIR Task resources. Normally at each exchange, the status of the Task changes to reflect the current status of the workflow, see also [FHIR Task State Machine](https://hl7.org/fhir/R4/task.html#statemachine).

[FHIR RESTful API](https://hl7.org/fhir/R4/http.html) is used in the examples below, other event notification methods may be used instead.

 ```
  POST https://primarycare.example.nhs.uk/FHIR/R4/Task
```

### Event Payload Example

{{pagelink:Home/FHIR-Assets/Examples/Task-Consent-Verification-Requested.page.md}}
