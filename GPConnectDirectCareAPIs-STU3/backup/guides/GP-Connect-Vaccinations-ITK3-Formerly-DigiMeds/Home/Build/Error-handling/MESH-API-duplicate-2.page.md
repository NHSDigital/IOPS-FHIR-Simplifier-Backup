## {{page-title}}

Please note that, when using the MESH API to send a message, errors encountered when using the automated registered practice routing will not be returned in the API response header or payload, but via a MESH error report `.CTL` file placed in the sending organisation MESH mailbox.

For example, where an invalid NHS Number has been supplied in the Mex_To HTTP header, an error report `.CTL` file will be returned with a `<StatusRecord>` section which provides error details as follows:

```xml
<StatusRecord>
    <DateTime>20170926135509</DateTime>
    <Event>SEND</Event>
    <Status>ERROR</Status>
    <StatusCode>EPL-152</StatusCode>
    <Description>Invalid NHS Number</Description>
  </StatusRecord>
```

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <b>Note</b>: The sender has the responsibility to inform an appropriate person if the following conditions are met.
</div>

- where a document is not successfully received / managed by the message receiver
- an ITK3 infastructure acknowledgement is not received
- an ITK3 business acknowledgement is not received