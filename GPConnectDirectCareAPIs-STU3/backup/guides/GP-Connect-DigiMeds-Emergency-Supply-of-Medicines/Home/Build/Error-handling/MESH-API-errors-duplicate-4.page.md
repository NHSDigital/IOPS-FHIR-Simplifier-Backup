## {{page-title}}

Please note that, when using the MESH API to send a message, errors encountered when using the automated registered practice routing will not be returned in the API response header or payload, but via a MESH error report .CTL file placed in the sending organisation MESH mailbox.

For example, where an invalid NHS Number has been supplied in the `Mex_To` HTTP header, an error report .CTL file will be returned with a `<StatusRecord>` section which provides error details as follows:

```xml
<StatusRecord>
    <DateTime>20170926135509</DateTime>
    <Event>SEND</Event>
    <Status>ERROR</Status>
    <StatusCode>EPL-152</StatusCode>
    <Description>Invalid NHS Number</Description>
  </StatusRecord>
```


- where a Consultation Report is not successfully received/managed by the message receiver, the sender system **MUST** inform an appropriate person

- where either the infrastructure or business acknowledgements, or both, are not received for a Consultation Report, the sender system **MUST** inform an appropriate person