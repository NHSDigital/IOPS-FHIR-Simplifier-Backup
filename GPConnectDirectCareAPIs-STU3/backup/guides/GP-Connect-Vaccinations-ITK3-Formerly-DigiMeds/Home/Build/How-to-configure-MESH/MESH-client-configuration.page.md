## {{page-title}}

When using the MESH client to send a message to the MESH server, the .CTL file will contain the following metadata about the message:

- `Version` **MUST** be the version of the document that is being sent - for example, the initial version will be `1`, and subsequent versions of updated / replaced documents will increment by 1

- `From_DTS` **MUST** contain the MESH mailbox ID of the sender of the message – for example, the originating organisation

- `To_DTS` **MUST** contain the NHS Number, DOB and Surname of the patient delimited by the underscore character `_`. This enables automatic routing of the message to the registered GP MESH mailbox

- `Subject` **MUST** contain a string based on the following format: `[document-title] for [patient-name], NHS Number: [nhs-number], seen at [location-name], [ods-code], Version: [version-number]`

- `LocalID` **MUST** contain the ODS code of the sending organisation

**Example**

```xml
<DTSControl>
    <Version>1</Version>
    <AddressType>DTS</AddressType>
    <MessageType>Data</MessageType>
    <From_DTS>GP0001</From_DTS>
    <To_DTS>GPPROVIDER_4857773456_09011955_Mowers</To_DTS>
    <Subject>[payload-title] for [patient-name], NHS Number: [nhs-number], seen at [practice-name], ODS code: [ods-code], version [version]</Subject>
    <LocalId>GP0001</LocalId>
    <DTSId></DTSId>
    <PartnerId></PartnerId>
    <Compress>Y</Compress>
    <Encrypted>N</Encrypted>
    <WorkflowId>DIGIMED_FLU_VAC</WorkflowId>
    <ProcessId></ProcessId>
    <DataChecksum></DataChecksum>
    <IsCompressed>Y</IsCompressed>
</DTSControl>
```