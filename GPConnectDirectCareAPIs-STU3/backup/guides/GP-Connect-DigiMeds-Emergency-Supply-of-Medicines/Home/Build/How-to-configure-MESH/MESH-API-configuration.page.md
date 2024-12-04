## {{page-title}}

When using the MESH API the Send Message API call will be used by a practice API client to send a message to the MESH server. MESH metadata items are defined in HTTP header fields as described below:

More information can be found in the [MESH documentation](https://digital.nhs.uk/developer/api-catalogue/message-exchange-for-social-care-and-health-api#post-/messageexchange/-mailbox_id-/outbox).


- `mex-from` **MUST** contain the MESH mailbox ID of the sender of the message – for example, the originating organisation

- `mex-to` **MUST** contain the NHS Number, DOB and Surname of the patient delimited by the underscore character `_`. This enables automatic routing of the message to the registered GP MESH mailbox

- `mex-subject` **MUST** contain a string based on the following format: `[payload-title] for [patient-name], NHS Number: [nhs-number], seen at [practice-name], ODS code: [ods-code], version [version]`

- `mex-localid` **MUST** contain the ODS code of the sending organisation

- `mex-workflowid` **MUST** contain the string `DIGIMED_FLU_VAC`

- `mex-localid` **MUST** contain the ODS code of the sending organisation

---