## `{{page-title}}`

This element has an open slice on `Observation.component`, and SHALL be used to record a systolic blood pressure measurement, which SHALL have a LOINC "magic code", in addition to the SNOMED CT concept used to record the type of systolic blood pressure measurement.

It SHOULD be used to also record a diastolic blood pressure measurement, which SHALL have a LOINC "magic code", in addition to the SNOMED CT concept used to record the type of diastolic blood pressure measurement if used.

The following values SHALL be used:

### `Observation.component:SystolicBP.code.coding:loinc`
The following SHALL be used for this profile:
- `Observation.code.coding.system` = `http://loinc.org`
- `Observation.code.coding.code` = `8480-6`
- `Observation.code.coding.display` = `Systolic blood pressure`

### `Observation.component:SystolicBP.code.coding:snomedCT`
The following SHALL be used for this profile:
- `Observation.component.code.coding.system` = `http://snomed.info/sct`
- `Observation.component.code.coding.code` = A SNOMED CT concept Id from {{pagelink:ValueSet-UKCore-BloodPressure-Systolic}}
- `Observation.component.code.coding.display` = The “preferred term” associated with the SNOMED CT concept

### `Observation.component:SystolicBP.value[x]`
The following SHALL be a Quantity, and the following used for this profile:
- `Observation.component.valueQuantity.system` = `http://unitsofmeasure.org`
- `Observation.component.valueQuantityg.code` = `mm[Hg]`
- `Observation.component.valueQuantity.unit` = `millimeter of mercury`

<br>

### `Observation.component:DiastolicBP.code.coding:loinc`
The following SHALL be used for this profile:
- `Observation.component.code.coding.system` = `http://loinc.org`
- `Observation.component.code.coding.code` = `8462-4`
- `Observation.component.code.coding.display` = `Diastolic blood pressure`

### `Observation.component:DiastolicBP.code.coding:snomedCT`
The following SHALL be used for this profile:
- `Observation.component.code.coding.system` = `http://snomed.info/sct`
- `Observation.component.code.coding.code` = A SNOMED CT concept Id from {{pagelink:ValueSet-UKCore-BloodPressure-Diastolic}}
- `Observation.component.code.coding.display` = The “preferred term” associated with the SNOMED CT concept

### `Observation.component:DiastolicBP.value[x]`
The following SHALL be a Quantity, and the following used for this profile:
- `Observation.component.valueQuantity.system` = `http://unitsofmeasure.org`
- `Observation.component.valueQuantity.code` = `mm[Hg]`
- `Observation.component.valueQuantity.unit` = `millimeter of mercury`

---