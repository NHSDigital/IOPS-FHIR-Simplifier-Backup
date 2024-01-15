---
parent: 
---
## How to construct a Bundle
A FHIR message is a set or a Bundle of resources passed between a source and a destination application, expecting some kind of action from the destination application. Two main types of messages exist: request messages and response messages. A request message is sent from a source application to a destination application whenever an event takes place such as the booking of an appointment or requesting an overview of all lab values. The destination application takes care of the request and replies with a response message. A FHIR message is a Bundle of type message. The first entry of the Bundle is always a MessageHeader resource. The MessageHeader specifies the message event (e.g. booking an appointment or linking two patients) in its code element. The MessageHeader may contain additional request metadata, such as the endpoint of the source application or the entity responsible for triggering the event (e.g. the practitioner booking the appointment). The focus element of the MessageHeader specifies the content of the message. The MessageHeader is followed by other resources depending on the type of request. For example, a request to book an appointment may contain the Patient to book the appointment for, the Practitioner to book the appointment with and the actual Appointment that is requested.

See  http://hl7.org/fhir/bundle.html for more information.

### Bundle overview
{{render:BundleOverview.png}}

### Sending the score only ###

The Bundle would contain a single Observation resource with the score populated in the Observation.value element. No observation.component elements with subscores would be present

### Sending the score along with the observations ###

The Bundle would contain an Observation resource with the score populated in the Observation.value element. The Subscores which were used to calculate the score would be carried in component.value elements.

### Sending the score whith the sub scores and the observations

The Bundle would contain a single Observation resource with the score populated in the Observation.value element. The Subscores which were used to calculate the score would be carried in component.value elements. The observations that were used as input for the scores are carried as derivedFrom observations.





