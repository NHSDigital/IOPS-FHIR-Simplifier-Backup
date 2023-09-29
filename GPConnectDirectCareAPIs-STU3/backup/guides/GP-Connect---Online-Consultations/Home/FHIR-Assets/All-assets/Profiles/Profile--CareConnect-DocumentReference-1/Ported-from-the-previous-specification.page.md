## {{page-title}}

- the `status` element **MUST** contain a fixed value of either `current`, `superseded` or `entered-in-error`
- the `type` element **MUST** contain a coded entry that references the type of document, this **SHOULD** be taken from SNOMED refset `1127551000000109`. Other classifications should be sent as text.
- the `subject` element **MUST** reference the `Patient` profile representing the `Patient` who is the subject of the document
- the `author` element **SHOULD** reference one of the following: a `Practitioner` resource profiled to `CareConnect-Practitioner-1`, an `Organization` resource profiled to `CareConnect-Organization-1`, a `Patient` resource profiled to `CareConnect-Patient-1`, a `RelatedPerson` resource profiled to `CareConnect-RelatedPerson-1`, a `Device` resource profiled to `ITK-Device-1`
- the `content` element **MUST** contain details about the document being referenced
- the `context` element **SHOULD** contain details about the clinical context of the document being referenced