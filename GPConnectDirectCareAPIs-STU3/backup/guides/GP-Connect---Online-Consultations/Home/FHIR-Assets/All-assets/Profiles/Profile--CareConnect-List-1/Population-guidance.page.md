## {{page-title}}

- a `List` containing references to all `Observation` resources that are captured **MUST** be populated if coded `Observation`s are being sent (the `List` resource in FHIR is used to manage collections of resources)
- the `status` element **MUST** contain a fixed value of `current`
- the `mode` element **MUST** contain a fixed value of `snapshot`
- the `title` element **MUST** contain the display element from the `code` field
- the `code` element **MUST** contain `826501000000100 - Miscellaneous record`
- the `subject` element **MUST** reference the `Patient` profile representing the `Patient` against whom the data was recorded
- the `entry.item` element **MUST** be populated to reference any/all `Observation` in the message