## {{page-title}}

A request to change the level of access a patient has can be made. Requests must be to increase the level of access. Lowering the level of access is not currently supported and will be rejected.

Each use case has the same basic request format providing information on the type of permission and the access level the request is for. For medical records there is an additional property so it is known whether the medical record's current or historical permissions should be updated.

### Request workflow

A `POST` request is made to the user permissions API with the appropriate payload based on the request the patient wants to make. Each request will be validated and if the validation passes, the request will be added to the GP system's workflow where it will be processed at some point in the future. Requests added to the workflow will be responded to with a state of `pending`.

Rejected requests are not added to the GP system's workflow. The text included in the response to a rejected request explains the reason for the rejection, this should be under details.text in the OperationOutcome. This should be displayed to the patient.

### Request handling

Pending requests will be listed on the response to getting a patient's permissions.

If a request is a duplicate, it is deduplicated by the GP system, with the original request being preserved.

If multiple requests are made (and accepted) they are combined within the workflow and reviewed together by a healthcare worker.