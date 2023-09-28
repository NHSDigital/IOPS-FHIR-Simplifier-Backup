## Derived Profile - Blood Pressure

<nocheck>
<div class="tab fhirTree">
 <button class="tablinks active" onclick="openTab(event, 'Tree View')">Tree View</button>
   <button class="tablinks" onclick="openTab(event, 'Table View')">Table View</button>
   <button class="tablinks" onclick="openTab(event, 'XML View')">XML View</button>
  <button class="tablinks" onclick="openTab(event, 'JSON View')">JSON View</button>
</div>

<div id="Tree View" class="tabcontent expandedProfile" style="display:block">
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation-VitalSigns-BloodPressure, buttons}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation-VitalSigns-BloodPressure}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation-VitalSigns-BloodPressure}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation-VitalSigns-BloodPressure}}
</div>
</nocheck>

The UKCore-Observation-VitalSigns-BloodPressure further derives from UKCore-Observation-VitalSigns, and this section only shows the differences between the two.

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


<hr class="thickline">