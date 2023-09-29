## {{page-title}}

- the `status` element **MUST** contain a fixed value of `preliminary` if unchecked by a clinician, or `final`
- the `category` element **SHOULD** contain high level category that represents the data in the `Observation`
- the `code` element **MUST** contain a clinical code that represents the data in the `Observation`
- the `subject` element **MUST** reference the `Patient` profile representing the `Patient` against whom the data was recorded
- the `issued` element **MUST** contain an audit trail timestamp representing when the data was recorded
- to ensure the `Observation` can be identified as patient entered data, the `performer` element **MUST** contain a reference to patient resource of the patient completing the online consultation
- the `value[x]` element **SHOULD** contain the value of the `Observation`
- the `component` element **SHOULD** be populated if recording a pair of results