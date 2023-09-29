## {{page-title}}

When using the MESH API the Send Message API call will be used by a practice API client to send a message to the MESH server. MESH metadata items are defined in HTTP header fields as described below:

- `Version` **MUST** be the version of the document that is being sent - for example, the initial version will be `1`, and subsequent versions of updated / replaced documents will increment by 1.

- `From_DTS` **MUST** contain the MESH mailbox ID of the sender of the message – for example, the originating organisation

- `To_DTS` **MUST** contain the NHS Number, DOB and Surname of the patient delimited by the underscore character `_`. This enables automatic routing of the message to the registered GP MESH mailbox

- `Subject` **MUST** contain To text in the following format: `[document-title] for [patient-name], NHS Number: [nhs-number], ODS code: [ods-code]`

- `LocalID` **MUST** contain the ODS code of the sending organisation
