## {{page-title}}

- the `status` element **MUST** contain a fixed value of `completed`
- the `subject` element **MUST** reference the `Patient` profile representing the `Patient` against whom the data was recorded
- the `authored` element **SHOULD** contain an audit trail timestamp representing when the data was recorded
- a set of `item` elements **MUST** contain the full online consultation questionnaire details
- the `item.linkId` element **MUST** contain a pointer specific to the questionnaire
- the `item.text` element **MUST** contain the question being asked
- the `item.answer.value[x]` element **MUST** contain the answer being given by the patient
- the `item.answer.value[x].valueReference` element **SHOULD** contain a reference to a resource, if applicable