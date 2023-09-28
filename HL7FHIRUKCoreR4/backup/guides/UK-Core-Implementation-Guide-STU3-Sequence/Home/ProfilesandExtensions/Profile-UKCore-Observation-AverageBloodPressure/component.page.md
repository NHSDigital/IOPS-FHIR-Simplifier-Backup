## `{{page-title}}`

This element has an open slice on `Observation.component`, and SHALL be used to record an average systolic blood pressure measurement, which SHALL have a SNOMED CT concept used to record the type of average systolic blood pressure measurement.

It SHOULD be used to also record an average diastolic blood pressure measurement, which SHALL have a SNOMED CT concept used to record the type of average diastolic blood pressure measurement.

The following values SHALL be used:

### `Observation.component:SystolicBP.code.coding:snomedCT`
The following SHALL be used for this profile:
- `Observation.component.code.coding.system` = `http://snomed.info/sct`
- `Observation.component.code.coding.code` = A SNOMED CT concept Id from {{pagelink:ValueSet-UKCore-BloodPressure-AverageSystolic}}
- `Observation.component.code.coding.display` = The “preferred term” associated with the SNOMED CT concept

### `Observation.component:SystolicBP.value[x]`
The following SHALL be a Quantity, and the following used for this profile:
- `Observation.component.valueQuantity.system` = `http://unitsofmeasure.org`
- `Observation.component.valueQuantityg.code` = `mm[Hg]`
- `Observation.component.valueQuantity.unit` = `millimeter of mercury`

<br>

### `Observation.component:DiastolicBP.code.coding:snomedCT`
The following SHALL be used for this profile:
- `Observation.component.code.coding.system` = `http://snomed.info/sct`
- `Observation.component.code.coding.code` = A SNOMED CT concept Id from {{pagelink:ValueSet-UKCore-BloodPressure-AverageDiastolic}}
- `Observation.component.code.coding.display` = The “preferred term” associated with the SNOMED CT concept

### `Observation.component:DiastolicBP.value[x]`
The following SHALL be a Quantity, and the following used for this profile:
- `Observation.component.valueQuantity.system` = `http://unitsofmeasure.org`
- `Observation.component.valueQuantity.code` = `mm[Hg]`
- `Observation.component.valueQuantity.unit` = `millimeter of mercury`