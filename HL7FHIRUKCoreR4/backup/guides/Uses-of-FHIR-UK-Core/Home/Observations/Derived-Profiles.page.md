## {{page-title}}

Proposed derived profiles for vital signs: Blood Pressure, BMI, Head Circumference, Heart Rate, Height, Oxygen Saturation Respiratory Rate, Temperature, and Weight. These will all be derived from <code>UKCore-Observation-VitalSigns</code>, and SHALL have a LOINC "magic code".

## Blood Pressure

The UKCore-Observation-VitalSigns-BloodPressure will further derive from UKCore-Observation-VitalSigns, and this section only shows the differences between the two.

### `Observation.code.coding:loinc`
The following SHALL be used for this profile:
- `Observation.code.coding.system` = `http://loinc.org`
- `Observation.code.coding.code` = `85354-9`
- `Observation.code.coding.display` = `Blood pressure panel with all children optional`

### `Observation.code.coding:snomedCT`
The following SHALL be used for this profile:
- `Observation.code.coding.system` = `http://snomed.info/sct`
- `Observation.code.coding.code` = `75367002`
- `Observation.code.coding.display` = `Blood pressure`

### `Observation.value[x]`
This element has a cardinality of 0..0, and SHALL NOT be present.

### `Observation.component:SystolicBP.code.coding:loinc`
The following SHALL be used for this profile:
- `Observation.code.coding.system` = `http://loinc.org`
- `Observation.code.coding.code` = `8480-6`
- `Observation.code.coding.display` = `Systolic blood pressure`

### `Observation.component:SystolicBP.code.coding:snomedCT`
The following SHALL be used for this profile:
- `Observation.component.code.coding.system` = `http://snomed.info/sct`
- `Observation.component.code.coding.code` = A SNOMED CT concept Id from https://fhir.hl7.org.uk/ValueSet/UKCore-BloodPressure-Systolic
- `Observation.component.code.coding.display` = The “preferred term” associated with the SNOMED CT concept

### `Observation.component:SystolicBP.value[x]`
The following SHALL be a Quantity, and the following used for this profile:
- `Observation.component.valueQuantity.system` = `http://unitsofmeasure.org`
- `Observation.component.valueQuantityg.code` = `mm[Hg]`
- `Observation.component.valueQuantity.unit` = `millimeter of mercury`

### `Observation.component:DiastolicBP.code.coding:loinc`
The following SHALL be used for this profile:
- `Observation.component.code.coding.system` = `http://loinc.org`
- `Observation.component.code.coding.code` = `8462-4`
- `Observation.component.code.coding.display` = `Diastolic blood pressure`

### `Observation.component:DiastolicBP.code.coding:snomedCT`
The following SHALL be used for this profile:
- `Observation.component.code.coding.system` = `http://snomed.info/sct`
- `Observation.component.code.coding.code` = A SNOMED CT concept Id from https://fhir.hl7.org.uk/ValueSet/UKCore-BloodPressure-Diastolic
- `Observation.component.code.coding.display` = The “preferred term” associated with the SNOMED CT concept

### `Observation.component:DiastolicBP.value[x]`
The following SHALL be a Quantity, and the following used for this profile:
- `Observation.component.valueQuantity.system` = `http://unitsofmeasure.org`
- `Observation.component.valueQuantity.code` = `mm[Hg]`
- `Observation.component.valueQuantity.unit` = `millimeter of mercury`

---

## BMI

The UKCore-Observation-VitalSigns-BMI further derives from UKCore-Observation-VitalSigns, and this section only shows the differences between the two.

### `Observation.code.coding:loinc`
The following SHALL be used for this profile:
- `Observation.code.coding.system` = `http://loinc.org`
- `Observation.code.coding.code` = `39156-5`
- `Observation.code.coding.display` = `Body mass index (BMI) [Ratio]`

### `Observation.code.coding:snomedCT`
The following SHALL be used for this profile:
- `Observation.code.coding.system` = `http://snomed.info/sct`
- `Observation.code.coding.code` =  A SNOMED CT concept Id from https://fhir.hl7.org.uk/ValueSet/UKCore-BMI
- `Observation.code.coding.display` = The “preferred term” associated with the SNOMED CT concept

### `Observation.value[x]`
For Adult BMI measurements, a <code>valueQuantity</code> SHALL be present, and the following used for this profile:
- `Observation.valueQuantity.system` = `http://unitsofmeasure.org`
- `Observation.valueQuantity.code` = `kg/m2`
- `Observation.valueQuantity.unit` = `kilogram / (meter ^ 2)`

For Child BMI measurements, a <code>valueQuantity</code> SHALL be present, and the following used for this profile:
- `Observation.valueQuantity.system` = `http://unitsofmeasure.org`
- `Observation.valueQuantity.code` = `{percentile}`
- `Observation.valueQuantity.unit` = 'Percentile`

---

## Head Circumference

The UKCore-Observation-VitalSigns-HeadCircumference further derives from UKCore-Observation-VitalSigns, and this section only shows the differences between the two.

### `Observation.code.coding:loinc`
The following SHALL be used for this profile:
- `Observation.code.coding.system` = `http://loinc.org`
- `Observation.code.coding.code` = `9843-4`
- `Observation.code.coding.display` = `Head Occipital-frontal circumference`

### `Observation.code.coding:snomedCT`
The following SHALL be used for this profile:
- `Observation.code.coding.system` = `http://snomed.info/sct`
- `Observation.code.coding.code` =  A SNOMED CT concept Id from https://fhir.hl7.org.uk/ValueSet/UKCore-HeadCircumference
- `Observation.code.coding.display` = The “preferred term” associated with the SNOMED CT concept

### `Observation.value[x]`
The following SHALL be a Quantity, and the following used for this profile:
- `Observation.valueQuantity.system` = `http://unitsofmeasure.org`
- `Observation.valueQuantityg.code` = `cm`
- `Observation.valueQuantity.unit` = `centimeter`

---

## Heart Rate

The UKCore-Observation-VitalSigns-HeartRate further derives from UKCore-Observation-VitalSigns, and this section only shows the differences between the two.

### `Observation.code.coding:loinc`
The following SHALL be used for this profile:
- `Observation.code.coding.system` = `http://loinc.org`
- `Observation.code.coding.code` = `8867-4`
- `Observation.code.coding.display` = `Heart rate`

### `Observation.code.coding:snomedCT`
The following SHALL be used for this profile:
- `Observation.code.coding.system` = `http://snomed.info/sct`
- `Observation.code.coding.code` =  A SNOMED CT concept Id from https://fhir.hl7.org.uk/ValueSet/UKCore-HeartRate
- `Observation.code.coding.display` = The “preferred term” associated with the SNOMED CT concept

### `Observation.value[x]`
The following SHALL be a Quantity, and the following used for this profile:
- `Observation.valueQuantity.system` = `http://unitsofmeasure.org`
- `Observation.valueQuantity.code` = `{beats}/min`
- `Observation.valueQuantity.unit` = `heart beats per minute`

---

## Height

he UKCore-Observation-VitalSigns-Height will further derive from UKCore-Observation-VitalSigns, and this section only shows the differences between the two.

### `Observation.code.coding:loinc`
The following SHALL be used for this profile:
- `Observation.code.coding.system` = `http://loinc.org`
- `Observation.code.coding.code` = `8302-2`
- `Observation.code.coding.display` = `Body height`

### `Observation.code.coding:snomedCT`
The following SHALL be used for this profile:
- `Observation.code.coding.system` = `http://snomed.info/sct`
- `Observation.code.coding.code` =  A SNOMED CT concept Id from https://fhir.hl7.org.uk/ValueSet/UKCore-LengthMeasurments
- `Observation.code.coding.display` = The “preferred term” associated with the SNOMED CT concept

### `Observation.value[x]`
The following SHALL be a Quantity, and the following used for this profile:
- `Observation.valueQuantity.system` = `http://unitsofmeasure.org`
- `Observation.valueQuantityg.code` = `m`
- `Observation.valueQuantity.unit` = `meter`

---

## Oxygen Saturation

he UKCore-Observation-VitalSigns-Height will further derive from UKCore-Observation-VitalSigns, and this section only shows the differences between the two.

### `Observation.code.coding:loinc`
The following SHALL be used for this profile:
- `Observation.code.coding.system` = `http://loinc.org`
- `Observation.code.coding.code` = `2708-6`
- `Observation.code.coding.display` = `Oxygen saturation in Arterial blood`

### `Observation.code.coding:snomedCT`
The following SHALL be used for this profile:
- `Observation.code.coding.system` = `http://snomed.info/sct`
- `Observation.code.coding.code` =  A SNOMED CT concept Id from https://fhir.hl7.org.uk/ValueSet/UKCore-OxygenSaturation
- `Observation.code.coding.display` = The “preferred term” associated with the SNOMED CT concept

### `Observation.value[x]`
The following SHALL be a Quantity, and the following used for this profile:
- `Observation.valueQuantity.system` = `http://unitsofmeasure.org`
- `Observation.valueQuantity.code` = `%`
- `Observation.valueQuantity.unit` = `percentage`

---

## Respiratory Rate

The UKCore-Observation-VitalSigns-RespiratoryRate further derives from UKCore-Observation-VitalSigns, and this section only shows the differences between the two.

### `Observation.code.coding:loinc`
The following SHALL be used for this profile:
- `Observation.code.coding.system` = `http://loinc.org`
- `Observation.code.coding.code` = `9279-1`
- `Observation.code.coding.display` = `Respiratory Rate`

### `Observation.code.coding:snomedCT`
The following SHALL be used for this profile:
- `Observation.code.coding.system` = `http://snomed.info/sct`
- `Observation.code.coding.code` =  A SNOMED CT concept Id from https://fhir.hl7.org.uk/ValueSet/UKCore-RespiratoryRate
- `Observation.code.coding.display` = The “preferred term” associated with the SNOMED CT concept

### `Observation.value[x]`
The following SHALL be a Quantity, and the following used for this profile:
- `Observation.valueQuantity.system` = `http://unitsofmeasure.org`
- `Observation.valueQuantity.code` = `{breaths}/min`
- `Observation.valueQuantity.unit` = `breaths per minute`

---

## Temperature

The UKCore-Observation-VitalSigns-Temperature further derives from UKCore-Observation-VitalSigns, and this section only shows the differences between the two.

### `Observation.code.coding:loinc`
The following SHALL be used for this profile:
- `Observation.code.coding.system` = `http://loinc.org`
- `Observation.code.coding.code` = `8310-5`
- `Observation.code.coding.display` = `Body temperature`

### `Observation.code.coding:snomedCT`
The following SHALL be used for this profile:
- `Observation.code.coding.system` = `http://snomed.info/sct`
- `Observation.code.coding.code` =  A SNOMED CT concept Id from https://fhir.hl7.org.uk/ValueSet/UKCore-Temperature
- `Observation.code.coding.display` = The “preferred term” associated with the SNOMED CT concept

### `Observation.value[x]`
The following SHALL be a Quantity, and the following used for this profile:
- `Observation.valueQuantity.system` = `http://unitsofmeasure.org`
- `Observation.valueQuantity.code` = `Cel`
- `Observation.valueQuantity.unit` = `degree Celsius`

---

## Weight

The UKCore-Observation-VitalSigns-Weight will further derive from UKCore-Observation-VitalSigns, and this section only shows the differences between the two.

### `Observation.code.coding:loinc`
The following SHALL be used for this profile:
- `Observation.code.coding.system` = `http://loinc.org`
- `Observation.code.coding.code` = `29463-7`
- `Observation.code.coding.display` = `Body weight`

### `Observation.code.coding:snomedCT`
The following SHALL be used for this profile:
- `Observation.code.coding.system` = `http://snomed.info/sct`
- `Observation.code.coding.code` =  A SNOMED CT concept Id from https://fhir.hl7.org.uk/ValueSet/UKCore-WeightMeasurments
- `Observation.code.coding.display` = The “preferred term” associated with the SNOMED CT concept

### `Observation.value[x]`
The following SHALL be a Quantity, and the following used for this profile:
- `Observation.valueQuantity.system` = `http://unitsofmeasure.org`
- `Observation.valueQuantityg.code` = `kg`
- `Observation.valueQuantity.unit` = `kilogram`

<hr class="thickline">