## {{page-title}}

Proposed derived profiles for clinical observations: ACVPU, Alcohol Consumption, Average blood Pressure, Blood Glucose, Inspired Oxygen and Tobacco Consumption. These will all be derived from <code>UKCore-Observation</code>, and do not have a LOINC "magic code".

All these derived profiles will share the following constraints to the UKCore-Observation:

### `status`

The following value SHALL be used:
- `Observation.status` = `final`

### `subject`

The cardinality of this element is 1..1, and the resource being referenced SHALL conform to the UKCore-Patient profile.

### `effective[x]`

The cardinality of this element is 1..1, and it SHALL be present.

---

## ACVPU

The UKCore-Observation-ACVPU derives from UKCore-Observation, and this section only shows the differences between the two.

### `Observation.code.coding`
The following SHALL be used for this profile:
- `Observation.code.coding.system` = `http://snomed.info/sct`
- `Observation.code.coding.code` = `1104441000000107`
- `Observation.code.coding.display` = `Alert Confusion Voice Pain Unresponsive scale score`

### `Observation.value[x]`
A <code>valueCodeableConcept</code> SHALL be present, and the following used for this profile:
- `Observation.valueCodeableConcept.system` = `http://snomed.info/sct`
- `Observation.valueCodeableConcept.code` = A SNOMED CT concept Id from https://fhir.hl7.org.uk/ValueSet/UKCore-ACVPU
- `Observation.valueCodeableConcept.display` = The “preferred term” associated with the SNOMED CT concept

---

## Alcohol Consumption

The UKCore-Observation-AlcoholConsumption derives from UKCore-Observation, and this section only shows the differences between the two.

### `Observation.category`
The following values SHALL be used:
- `Observation.category.coding.system` = `http://terminology.hl7.org/CodeSystem/observation-category`
- `Observation.category.coding.code` = `social-history`
- `Observation.category.coding.display` = `Social History`

### `Observation.code.coding`
The following SHALL be used for this profile:
- `Observation.code.coding.system` = `http://snomed.info/sct`
- `Observation.code.coding.code` = A SNOMED CT concept Id from https://fhir.hl7.org.uk/ValueSet/UKCore-AlcoholConsumption
- `Observation.code.coding.display` = The “preferred term” associated with the SNOMED CT concept

### `Observation.value[x]`
A <code>valueQuantity</code> SHALL be present, and the following used for this profile:
- `Observation.valueQuantity.system` = `http://unitsofmeasure.org`
- `Observation.valueQuantity.code` = `{drinks}/d`
- `Observation.valueQuantity.unit` = `drinks per day`

---

## Average Blood Pressure

The UKCore-Observation-AverageBloodPressure derives from UKCore-Observation, and this section only shows the differences between the two.

### `Observation.code.coding`
The following SHALL be used for this profile:
- `Observation.code.coding.system` = `http://snomed.info/sct`
- `Observation.code.coding.code` =  A SNOMED CT concept Id from https://fhir.hl7.org.uk/ValueSet/UKCore-BloodPressure-Average
- `Observation.code.coding.display` = The “preferred term” associated with the SNOMED CT concept

### `Observation.component:SystolicBP.code.coding`
The following SHALL be used for this profile:
- `Observation.component.code.coding.system` = `http://snomed.info/sct`
- `Observation.component.code.coding.code` = A SNOMED CT concept Id from https://fhir.hl7.org.uk/ValueSet/UKCore-BloodPressure-AverageSystolic
- `Observation.component.code.coding.display` = The “preferred term” associated with the SNOMED CT concept

### `Observation.component:SystolicBP.value[x]`
The following SHALL be a Quantity, and the following used for this profile:
- `Observation.component.valueQuantity.system` = `http://unitsofmeasure.org`
- `Observation.component.valueQuantityg.code` = `mm[Hg]`
- `Observation.component.valueQuantity.unit` = `millimeter of mercury`

### `Observation.component:DiastolicBP.code.coding`
The following SHALL be used for this profile:
- `Observation.component.code.coding.system` = `http://snomed.info/sct`
- `Observation.component.code.coding.code` = A SNOMED CT concept Id from https://fhir.hl7.org.uk/ValueSet/UKCore-BloodPressure-AverageDiastolic
- `Observation.component.code.coding.display` = The “preferred term” associated with the SNOMED CT concept

### `Observation.component:DiastolicBP.value[x]`
The following SHALL be a Quantity, and the following used for this profile:
- `Observation.component.valueQuantity.system` = `http://unitsofmeasure.org`
- `Observation.component.valueQuantity.code` = `mm[Hg]`
- `Observation.component.valueQuantity.unit` = `millimeter of mercury`

---

## Blood Glucose

The UKCore-Observation-BloodGlucose derives from UKCore-Observation, and this section only shows the differences between the two.

### `Observation.code.coding`
The following SHALL be used for this profile:
- `Observation.code.coding.system` = `http://snomed.info/sct`
- `Observation.code.coding.code` = A SNOMED CT concept Id from https://fhir.hl7.org.uk/ValueSet/UKCore-BloodGlucose
- `Observation.code.coding.display` = The “preferred term” associated with the SNOMED CT concept

### `Observation.value[x]`
A <code>valueQuantity</code> SHALL be present, and the following used for this profile:
- `Observation.valueQuantity.system` = `http://unitsofmeasure.org`
- `Observation.valueQuantity.code` = `mmol/L`
- `Observation.valueQuantity.unit` = `millimoles per litre`

---

## Inspired Oxygen

The UKCore-Observation-InspiredOxygen derives from UKCore-Observation, and this section only shows the differences between the two.

### `Observation.code.coding`
The following SHALL be used for this profile:
- `Observation.code.coding.system` = `http://snomed.info/sct`
- `Observation.code.coding.code` = A SNOMED CT concept Id from https://fhir.hl7.org.uk/ValueSet/UKCore-InspiredOxygen
- `Observation.code.coding.display` = The “preferred term” associated with the SNOMED CT concept

### `Observation.value[x]`
A <code>valueQuantity</code> SHOULD be present, and the following used for this profile:
- `Observation.valueQuantity.system` = `http://unitsofmeasure.org`
- `Observation.valueQuantity.code` = `l/min`
- `Observation.valueQuantity.unit` = `litre per minute`

---

## Tobacco Consumption

The UKCore-Observation-TobaccoConsumption derives from UKCore-Observation, and this section only shows the differences between the two.

### `Observation.category`
The following values SHALL be used:
- `Observation.category.coding.system` = `http://terminology.hl7.org/CodeSystem/observation-category`
- `Observation.category.coding.code` = `social-history`
- `Observation.category.coding.display` = `Social History`

### `Observation.code.coding`
The following SHALL be used for this profile:
- `Observation.code.coding.system` = `http://snomed.info/sct`
- `Observation.code.coding.code` = A SNOMED CT concept Id from https://fhir.hl7.org.uk/ValueSet/UKCore-TobaccoConsumption
- `Observation.code.coding.display` = The “preferred term” associated with the SNOMED CT concept

### `Observation.value[x]`
A <code>valueQuantity</code> SHALL be present, and the following used for this profile:
- `Observation.valueQuantity.system` = `http://unitsofmeasure.org`
- `Observation.valueQuantity.code` = `{#}/d`
- `Observation.valueQuantity.unit` = `number smoked per day`

<hr class="thickline">