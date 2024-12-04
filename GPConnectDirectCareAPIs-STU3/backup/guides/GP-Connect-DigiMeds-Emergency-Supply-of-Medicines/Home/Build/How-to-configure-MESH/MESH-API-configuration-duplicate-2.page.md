## {{page-title}}

When using the MESH API the Send Message API call will be used by a sending organisation API client to send a message to the MESH server. MESH metadata items are defined in HTTP header fields as described below:

`Mex-From` **MUST** contain the MESH mailbox ID of the sender of the message – in this case the originating organisation

`Mex-To` **MUST** contain the MESH mailbox ID of the receiver of the message – in this case either the mailbox ID for the patient's registered GP practice, or chosen community pharmacy

`Mex-Subject` **MUST** contain To text in the following format: 

```
[title of document] for patient: [patient name], NHS number: [NHS Number], ODS code: [ODS Code]
```

`LocalID` **MUST** contain the ODS code of the sending organisation

An example `.CTL` file is given below for a Consultation Report message regarding a consultation which took place for a fictional patient: 

- Patient name: Mrs Anne Teak
- NHS number: 1234567890
- Date of birth: 9th January 1955
- ODS code: GP0001

```xml
<DTSControl>
    <Version>1.0</Version>
    <AddressType>DTS</AddressType>
    <MessageType>Data</MessageType>
    <From_DTS>GP0001</From_DTS>
    <To_DTS>GPPROVIDER_1234567890_09011955_Smith</To_DTS>
    <Subject>Online consultation report for Mrs Anne Teak, NHS Number 1234567890, GP0001</Subject>
    <LocalId>GP0001</LocalId>
    <DTSId></DTSId>
    <PartnerId></PartnerId>
    <Compress>Y</Compress>
    <Encrypted>N</Encrypted>
    <WorkflowId>GPFED_CONSULT_REPORT</WorkflowId>
    <ProcessId></ProcessId>
    <DataChecksum></DataChecksum>
    <IsCompressed>Y</IsCompressed>
</DTSControl>
```