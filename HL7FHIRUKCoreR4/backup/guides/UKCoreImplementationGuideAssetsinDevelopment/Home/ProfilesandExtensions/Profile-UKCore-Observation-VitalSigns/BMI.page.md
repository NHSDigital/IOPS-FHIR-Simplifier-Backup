## Derived Profile - BMI

<nocheck>
<div class="tab fhirTree">
 <button class="tablinks active" onclick="openTab(event, 'Tree View')">Tree View</button>
   <button class="tablinks" onclick="openTab(event, 'Table View')">Table View</button>
   <button class="tablinks" onclick="openTab(event, 'XML View')">XML View</button>
  <button class="tablinks" onclick="openTab(event, 'JSON View')">JSON View</button>
</div>

<div id="Tree View" class="tabcontent expandedProfile" style="display:block">
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation-VitalSigns-BMI, buttons}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation-VitalSigns-BMI}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation-VitalSigns-BMI}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation-VitalSigns-BMI}}
</div>
</nocheck>

The UKCore-Observation-VitalSigns-BMI further derives from UKCore-Observation-VitalSigns, and this section only shows the differences between the two.

### `Observation.code.coding:loinc`
The following SHALL be used for this profile:
- `Observation.code.coding.system` = `http://loinc.org`
- `Observation.code.coding.code` = `8302-2`
- `Observation.code.coding.display` = `Body height`

### `Observation.code.coding:snomedCT`
The following SHALL be used for this profile:
- `Observation.code.coding.system` = `http://snomed.info/sct`
- `Observation.code.coding.code` =  A SNOMED CT concept Id from https://fhir.hl7.org.uk/ValueSet/UKCore-BMI
- `Observation.code.coding.display` = The “preferred term” associated with the SNOMED CT concept

### `Observation.value[x]`
The following SHALL be a Quantity, and the following used for this profile:
- `Observation.valueQuantity.system` = `http://unitsofmeasure.org`
- `Observation.valueQuantityg.code` = `cm`
- `Observation.valueQuantity.unit` = `centimeter`

<hr class="thickline">