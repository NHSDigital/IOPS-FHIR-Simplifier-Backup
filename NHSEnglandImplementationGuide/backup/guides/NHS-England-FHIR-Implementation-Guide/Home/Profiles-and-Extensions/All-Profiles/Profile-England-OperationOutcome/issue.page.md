## `issue`

<b>Definition:</b><br>
An error, warning, or information message that results from a system action.

### `issue.severity`

Indicates whether the issue indicates a variation from successful processing.

### `issue.code`

Describes the type of the issue. The system that creates an OperationOutcome SHALL choose the most applicable code from the IssueType value set, and may additional provide its own code for the error in the details element.

### `issue.details`

Additional details about the error. This may be a text description of the error or a system code that identifies the error.

### `issue.expression`

FHIRPath of element(s) related to issue.