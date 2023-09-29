## {{page-title}}

- the `status` element **MUST** contain a fixed value of `requested`
- the `statusReason` element **SHOULD** contain a code to identify the reason for the current status
- the `intent` element **MUST** contain a fixed value of either `proposal`, `plan`, or `order`, to distinguish whether the task is a proposal, plan or full order
- the `priority` element **SHOULD** contain a fixed value of either `normal`, `urgent`, `asap`, or `stat`
- the `code` element **SHOULD** contain codes to identify what the task involves. These will typically be specific to a particular workflow
- the `for` element **SHOULD** contain a reference to the patient
- the `context` element **SHOULD** contain a reference to the encounter which this task originated
- the `requester.agent` element **SHOULD** reference one of the following: a `Practitioner` resource profiled to `CareConnect-Practitioner-1`, an `Organization` resource profiled to `CareConnect-Organization-1`, a `Patient` resource profiled to `CareConnect-Patient-1`, a `RelatedPerson` resource profiled to `CareConnect-RelatedPerson-1`, a `Device` resource profiled to `ITK-Device-1`
- the `owner` element **SHOULD** contain a reference to a resource responsible for the task execution
- the `reason` element **SHOULD** contain details explaining why the task is needed
- the `note` element **SHOULD** contain comments made about the task
- the `restriction` element **SHOULD** be populated if there are any limitations on what parts of the referenced request should be actioned
- the `input` element **SHOULD** contain additional information that may be needed in the execution of the task
- the `output` element **SHOULD** contain any outputs produced by the task