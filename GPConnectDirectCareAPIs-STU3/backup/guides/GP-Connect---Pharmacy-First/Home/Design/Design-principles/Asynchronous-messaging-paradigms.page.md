## {{page-title}}

Messages flowing into GP practices on MESH will arise mainly from the following two patterns of event notification:

**1. Point-to-point event notification**

Where the message sender knows which party or parties the message is intended for, a point-to-point event notification is often used. Here the sender directs the message to a known recipient or set of recipients.

For example, this specification uses this pattern. The sending practice knows that the payload is intended only for a single known recipient organisation - the registered practice of the patient. Therefore, this pattern is used for this use case and the MESH Endpoint Lookup Service is used as a broker to facilitate this message delivery pattern.


**2. Publish/Subscribe event notification**

This pattern would be more applicable where a healthcare event has taken place, but the message sender does not know all the parties who are interested in that event.

In this model, organisations will subscribe through an event hub to those events in which they have a legitimate interest. The sender publishes an event to this event hub, and all the subscribers to the event will receive the event details.

---