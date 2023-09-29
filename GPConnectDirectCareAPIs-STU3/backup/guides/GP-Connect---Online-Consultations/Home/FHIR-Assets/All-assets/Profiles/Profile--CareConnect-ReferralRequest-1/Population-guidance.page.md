## {{page-title}}

- the `status` element **MUST** contain a fixed value of `unknown`
- the `intent` element **MUST** contain a fixed value of `order`
- the `priority` element **SHOULD** reference a priority code. A mapping is applied to the priority codes to align it to the e-Referral Service priority types. This **MUST** be populated where the source system has a referral priority which matches the e-Referral Service priority codes or can be mapped to those priority codes. If there is a priority code for the referral but it is incompatible with the e-Referral Service priorities, this element **MUST** be excluded and the priority **MUST** be supplied in the note element
- the `subject` element **MUST** reference the `Patient` profile representing the `Patient` who is the subject of the referral
- the `context` element **SHOULD** reference the `Encounter within which the referral was recorded
- the `requester` element **SHOULD** reference the details of the person, practitioner or organisation responsible for the decision to refer the patient or, if is not attributed specifically, then populate with the recorder
- the `requester.agent` element **MUST** reference one of the following: a `Practitioner` resource profiled `to CareConnect-Practitioner-1`, an `Organization` resource profiled to `CareConnect-Organization-1`, a `Patient` resource profiled to `CareConnect-Patient-1`, a `RelatedPerson` resource profiled to `CareConnect-RelatedPerson-1`, a `Device` resource profiled to `ITK-Device-1`
- the `recipient` element **SHOULD** be populated with the practitioner and/or organisation the patient has been referred to, if that is recorded in a suitable coded format
- the `reasonCode` element **SHOULD** be populated with the source system’s main coded entry for the referral
- the `description` element **SHOULD** be populated with a free text description associated with the referral
- the `supportingInfo` element **SHOULD** contain a reference to the referral letter(s) and any other supporting documents or resources which are not covered by other more specific elements, for instance this could include reference to linked observations