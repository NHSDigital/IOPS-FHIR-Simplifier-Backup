## `{{page-title}}`

The following values SHALL be used:

### `Observation.code.coding:loinc`
The following SHALL be used for this profile:
- `Observation.code.coding.system` = `http://loinc.org`
- `Observation.code.coding.code` = `85354-9`
- `Observation.code.coding.display` = `Blood pressure panel with all children optional`

### `Observation.code.coding:snomedCT`
The following SHALL be used for this profile:
- `Observation.code.coding.system` = `http://snomed.info/sct`
- `Observation.code.coding.code` = A SNOMED CT concept Id from {{pagelink:ValueSet-UKCore-BloodPressure}}
- `Observation.code.coding.display` = The “preferred term” associated with the SNOMED CT concept

---