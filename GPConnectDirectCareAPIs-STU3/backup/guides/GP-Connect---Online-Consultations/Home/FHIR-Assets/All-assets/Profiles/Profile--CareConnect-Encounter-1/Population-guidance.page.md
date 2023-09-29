## {{page-title}}

- the `status` element **MUST** contain a fixed value of `finished`
- the `type` element **MUST** contain a valid SNOMED code for the type encounter being sent, for example `149971000000103 (Encounter using general practice online consultation system (procedure))`
- the `subject` element **MUST** reference the `Patient` profile representing the `Patient` who is the subject of the encounter
- the `participant` element **SHOULD** reference the `Practitioner` profile or the `RelatedPerson` profile if applicable
- the `priority` element **SHOULD** reference a priority code, by default this value should be `R` meaning `routine`
- the `period` element **SHOULD** be populated with the start and end time of the encounter captured in the source system
- the `serviceProvider` element **SHOULD** contain a reference to the organisation responsible for the encounter