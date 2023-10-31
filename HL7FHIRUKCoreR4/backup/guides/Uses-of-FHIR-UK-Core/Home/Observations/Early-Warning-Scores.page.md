## {{page-title}}

Proposed derived profiles for early warning scores: Early Warning Total Score. This will all be derived from <code>UKCore-Observation</code>, and does not have a LOINC "magic code".

All these derived profiles will share the following constraints to the UKCore-Observation:

### `status`

The following value SHALL be used:
- `Observation.status` = `final`

### `category`
The following values SHALL be used:
- `Observation.category.coding.system` = `http://terminology.hl7.org/CodeSystem/observation-category`
- `Observation.category.coding.code` = `survey`
- `Observation.category.coding.display` = `Survey`

### `code`
The following SHALL be used for this profile:
- `Observation.code.coding.system` = `http://snomed.info/sct`
- `Observation.code.coding.code` = A SNOMED CT concept Id from https://fhir.hl7.org.uk/ValueSet/UKCore-EarlyWarningTotalScores
- `Observation.code.coding.display` = The “preferred term” associated with the SNOMED CT concept

### `subject`

The cardinality of this element is 1..1, and the resource being referenced SHALL conform to the UKCore-Patient profile.

### `effective[x]`

The cardinality of this element is 1..1, and it SHALL be present.

### `value[x]`
A <code>valueQuantity</code> SHALL be present, and the following used for this profile:
- `Observation.valueQuantity.system` = `http://unitsofmeasure.org`
- `Observation.valueQuantity.code` = `{ScoreOf}`

### `derivedFrom`
This element SHOULD be populated with a referenced resources conforming to UKCore-Observation, and these resources should be the observations used to determine the Early warning Score component sub scores.

### `component`
This element SHOULD be used to record the component sub scores used to determine the total score

The following values SHALL be used:

### `component.code.coding`
The following SHALL be used for this profile:
- `Observation.component.code.coding.system` = `http://snomed.info/sct`
- `Observation.component.code.coding.code` = A SNOMED CT concept Id from https://fhir.hl7.org.uk/ValueSet/UKCore-EarlyWarningSubScore
- `Observation.component.code.coding.display` = The “preferred term” associated with the SNOMED CT concept

### `component.value[x]`
The following SHALL be a Quantity, and the following used for this profile:
- `Observation.component.valueQuantity.system` = `http://unitsofmeasure.org`
- `Observation.component.valueQuantityg.code` = `{ScoreOf}`
