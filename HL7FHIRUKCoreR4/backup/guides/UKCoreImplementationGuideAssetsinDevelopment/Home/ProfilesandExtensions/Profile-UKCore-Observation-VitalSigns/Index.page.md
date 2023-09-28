---
topic: Profile-Observation-VitalSigns
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation-VitalSigns
---

# StructureDefinition-UKCore-Observation-VitalSigns

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'UKCoreObservationVitalSigns'
select
	Canonical_URL: url,
  Current_Version: version,
  Last_Updated: date,
	Description: description
```
</div>
<br>

@```
from
	StructureDefinition
where
	name = 'UKCoreObservationVitalSigns'
select
	Profile_Purpose: purpose
```

<nocheck>
<div class="tab fhirTree">
 <button class="tablinks active" onclick="openTab(event, 'Tree View')">Tree View</button>
   <button class="tablinks" onclick="openTab(event, 'Table View')">Table View</button>
   <button class="tablinks" onclick="openTab(event, 'XML View')">XML View</button>
  <button class="tablinks" onclick="openTab(event, 'JSON View')">JSON View</button>
  <button class="tablinks" onclick="openTab(event, 'Examples')">Examples</button>
  <button class="tablinks" onclick="openTab(event, 'Usage')">Usage</button>
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

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>

</div>
<div id="Usage" class="tabcontent">
  <h3>Usage</h3>

</div>

</nocheck>

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core Observation-VitalSigns profile:

- Reord or Query for a specific patient vital signs

<hr class="thickline">

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
