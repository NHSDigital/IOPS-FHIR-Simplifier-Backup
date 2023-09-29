## {{page-title}}

- the `status` element **MUST** contain a fixed value of either `partial`, `completed`, `entered-in-error`, or `health-unknown`
- the `patient` element **MUST** contain a reference to the patient that the history is about
- the `relationship` element **MUST** contain a coded entry describing the nature of the relationship between the patient and the related person being described in the family history
- the `reasonReference` element **SHOULD** reference one of the following: a `QuestionnaireResponse` resource profiled to `CareConnect-QuestionnaireResponse-1`, an `Observation` resource profiled to `CareConnect-Observation-1`, a `AllergyIntolerance` resource profiled to `CareConnect-AllergyIntolerance-1`
- the `note` element **SHOULD** contain all text associated with the related person
- the `condition` element **SHOULD** contain the details of the condition that the related person had