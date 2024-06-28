## {{page-title}}

The flow of messages through MESH is controlled through rules which are set in the following form:

`Mailbox ID` is allowed to `Send|Receive` messages with `Workflow ID`

For example, to enable a consultation report message to flow from `GP0001` to `GP0002`, two rules need to be set up in MESH configuration:

- `GP0001` is allowed to `Send` messages with workflow ID `GPFED_CONSULT_REPORT`
- `GP0002` is allowed to `Receive` messages with workflow ID `GPFED_CONSULT_REPORT_ACK`

As GP Connect Messaging capabilities are delivered, MESH will therefore be configured to enable actual message flow between organisations. Note that the approach is based on explicit opt-in to ensure particular GP practices receive only those messages which they have consented to receive.