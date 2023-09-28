## `{{page-title}}`

The cardinality of this element is 1..1, and it SHALL be present.

This element has an closed slice, and SHALL be used to differentiate between a vital signs observation and a survey observation.

### `Observation.category:vitalSigns`
The following SHOULD be used for this profile:
- `Observation.category.coding.system` = `http://terminology.hl7.org/CodeSystem/observation-category`
- `Observation.category.coding.code` = `vital-signs`
- `Observation.category.coding.display` = `Vital Signs`.

### `Observation.category:survey`
The following SHOULD be used for this profile:
- `Observation.category.coding.system` = `http://terminology.hl7.org/CodeSystem/observation-category`
- `Observation.category.coding.code` = `survey`
- `Observation.category.coding.display` = `Survey`.

---