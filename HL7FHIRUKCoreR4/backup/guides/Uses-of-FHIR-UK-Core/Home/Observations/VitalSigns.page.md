## {{page-title}}

<nocheck>
<div class="tab fhirTree">
 <button class="tablinks active" onclick="openTab(event, 'Tree View')">Tree View</button>
   <button class="tablinks" onclick="openTab(event, 'Table View')">Table View</button>
   <button class="tablinks" onclick="openTab(event, 'XML View')">XML View</button>
  <button class="tablinks" onclick="openTab(event, 'JSON View')">JSON View</button>
</div>

<div id="Tree View" class="tabcontent expandedProfile" style="display:block">
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation-VitalSigns, buttons}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json}}
</div>
</nocheck>

---

## Profile Specific Implementation Guidance: ##

This is a derived profile of UKCore-Observation and this page only shows the differences between the two. Refer to the base Profile for more implementation guidance.

This guidance is also designed to align with https://build.fhir.org/observation-vitalsigns.html where possible.

### Minimum Viable Content

The minimum viable content that all provider and consumer systems SHALL support are the elements within the corresponding UKCore-Observation table, along with the following.

<table class="assets">
<tr>
<th width="30%">Element</th>
<th width="70%">Reason</th>
</tr>
<tr>
<td><code>Observation.category</code></td>
<td>A category of Vital Signs or Survey SHALL be present.</td>
</tr>
<tr>
<td><code>Observation.code.coding</code></td>
<td>If the category is Vital Signs, a LOINC "magic code" SHALL be present in addition to the SNOMED CT concept for the observation type.</td>
</tr>
<tr>
<td><code>Observation.subject</code></td>
<td>A UKCore-Patient SHALL be present.</td>
</tr>
<tr>
<td><code>Observation.effective[x]</code></td>
<td>A an effective time or date SHALL be present.</td>
</tr>
<tr>
<td><code>Observation.component.copde.coding</code></td>
<td>If the category is Vital Signs, a LOINC "magic code" SHALL be present in addition to the SNOMED CT concept for the observation type.</td>
</tr>
</table>

---

## Bindings (differential)

More information about the bindings to UK Core ValueSets, and other ValueSets different to UK Core Observation can be found below.

<table class="assets">
<tr>
<th width="30%">Context</th>
<th width="20%">Strength</th>
<th width="50%">Link</th>
</tr>
<tr>
<td>Observation.code.coding:loinc</td>
<td>Extensible</td>
<td>http://hl7.org/fhir/ValueSet/observation-vitalsignresult</td>
</tr>
<tr>
<td>Observation.code.coding:snomedCT</td>
<td>Preferred</td>
<td>https://fhir.hl7.org.uk/ValueSet/UKCore-ObservationVitalSignsTyp</td>
</tr>
</table>

---

## Constraints (differential)

More information about the constraints on the <code>UKCore-Observation-VitalSigns</code> profile can be found below.

<table class="assets">
<tr>
<th width="15%">Key</th>
<th width="10%">Severity</th>
<th width="30%">Expression</th>
<th width="45%">Human Description</th>
</tr>
<tr>
<td>ukcore-obs-vs-001</td>
<td>error</td>
<td>
<code>category</code>.where(<code>code</code>='vital-signs').exists() implies <code>code.coding</code>.where(<code>system</code>='http://loinc.org').exists()
</td>
<td>Where the category is Vital Signs the code.coding SHALL include a LOINC "magic code"</td>
</tr>
</table>

---

## `status`

The following value SHALL be used:
- `Observation.status` = `final`

---

## `category`

The cardinality of this element is 1..1, and it SHALL be present. The following SHALL be used for this profile:
- `Observation.category.coding.system` = `http://terminology.hl7.org/CodeSystem/observation-category`
- `Observation.category.coding.code` = `vital-signs`
- `Observation.category.coding.display` = `Vital Signs`

---

## `code`

This element has an open slice on `Observation.code.coding`, and MAY be used to send a SNOMED CT concept for the type of observation, and where the `Observation.category` is `Vital Signs`, SHALL also contain a LOINC "magic code" for the type of vital sign observation.

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

## `subject`

The cardinality of this element is 1..1, and the resource being referenced SHALL conform to the UKCore-Patient profile.

---

## `effective[x]`

The cardinality of this element is 1..1, and it SHALL be present.


<hr class="thickline">