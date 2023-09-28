## `{{page-title}}`

This element has an open slice on `Observation.code.coding`, and MAY be used to send a SNOMED CT concept for the type of observation, and SHALL also contain a LOINC "magic code" for the type of vital sign observation.

### `Observation.code.coding:loinc`
The following SHALL be used for this profile, where the `Observation.category` is `Vital Signs`:
- `Observation.code.coding.system` = `http://loinc.org`
- `Observation.code.coding.code` = A LOINC "magic code" from http://hl7.org/fhir/ValueSet/observation-vitalsignresult
- `Observation.code.coding.display` = The display value for the LOINC code

### `Observation.code.coding:snomedCT`
The following SHOULD be used for this profile:
- `Observation.code.coding.system` = `http://snomed.info/sct`
- `Observation.code.coding.code` = A SNOMED CT concept Id from https://fhir.hl7.org.uk/ValueSet/UKCore-ObservationVitalSignsType
- `Observation.code.coding.display` = The “preferred term” associated with the SNOMED CT concept

---