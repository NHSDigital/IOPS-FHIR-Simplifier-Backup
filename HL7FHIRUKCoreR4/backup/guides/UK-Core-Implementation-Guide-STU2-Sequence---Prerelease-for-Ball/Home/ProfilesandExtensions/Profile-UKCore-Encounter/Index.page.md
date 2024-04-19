---
topic: Profile-Encounter-79976
---
# StructureDefinition-UKCore-Encounter

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'UKCoreEncounter'
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
	name = 'UKCoreEncounter'
select
	Profile_Purpose: purpose
```

<nocheck>
<div class="tab fhirTree">
 <button class="tablinks active" onclick="openTab(event, 'Snapshot View')">Snapshot View</button>
  <button class="tablinks" onclick="openTab(event, 'Differential View')">Differential View</button>
  <button class="tablinks" onclick="openTab(event, 'Hybrid View')">Hybrid View</button>
   <button class="tablinks" onclick="openTab(event, 'Table View')">Table View</button>
   <button class="tablinks" onclick="openTab(event, 'XML View')">XML View</button>
  <button class="tablinks" onclick="openTab(event, 'JSON View')">JSON View</button>
  <button class="tablinks" onclick="openTab(event, 'Examples')">Examples</button>
</div>

<div id="Snapshot View" class="tabcontent" style="display:block">
  <h3>Snapshot View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Encounter, snapshot}}
</div>

<div id="Differential View" class="tabcontent">
  <h3>Differential View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Encounter, diff}}
</div>

<div id="Hybrid View" class="tabcontent">
  <h3>Hybrid View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Encounter, hybrid}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Encounter, snapshot}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Encounter, snapshot}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Encounter, snapshot}}
</div>

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
<b>Inpatient Encounter</b> - An example to illustrate an inpatient encounter.
<br>{{pagelink:Example-UKCore-Encounter-InpatientEncounter}}
</div>
</nocheck>

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core Encounter profile:

- Query for a specific patient encounter
- Query for recent patient encounters
- Record or update an encounter

---

## Profile Specific Implementation Guidance: ##

### Mandatory and Must Support Data Elements

The following elements are identified as MustSupport, and it is expected that consumers and suppliers SHALL support these as per the {{pagelink:Guidance-MustSupport-25267}}.

<table class="assets">
<tr>
<th width="30%">Element</th>
<th width="70%">Reason</th>
</tr>
<tr>
<td><code>Encounter.identifier</code></td>
<td>Identifier(s) by which this encounter is known.</td>
</tr>
<tr>
<td><code>Encounter.status</code></td>
<td>The status of the encounter with the subject.</td>
</tr>
<tr>
<td><code>Encounter.class</code></td>
<td>Concepts representing classification of patient encounter such as ambulatory (outpatient), inpatient, emergency, home health or others due to local variations.</td>
</tr>
<tr>
<td><code>Encounter.subject</code></td>
<td>The patient or group present at the encounter.</td>
</tr>
<tr>
<td><code>Encounter.participant</code></td>
<td>The list of people responsible for providing the service.</td>
</tr>
<tr>
<td><code>Encounter.reasonCode</code></td>
<td>Reason the encounter takes place, expressed as a code. For admissions, this can be used for a coded admission diagnosis.</td>
</tr>
<tr>
<td><code>Encounter.reasonReference</code></td>
<td>Reason the encounter takes place, expressed as a reference to a Condition, Procedure, Observation, or ImmunizationRecommendation.</td>
</tr>
</table>

---