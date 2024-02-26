---
topic: Profile-Observation-Lab-67452
---

# StructureDefinition-UKCore-Observation-Lab

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'UKCoreObservationLab'
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
	name = 'UKCoreObservationLab'
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
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation-Lab, snapshot}}
</div>

<div id="Differential View" class="tabcontent">
  <h3>Differential View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation-Lab, diff}}
</div>

<div id="Hybrid View" class="tabcontent">
  <h3>Hybrid View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation-Lab, hybrid}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation-Lab, snapshot}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation-Lab, snapshot}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation-Lab, snapshot}}
</div>

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
<b>Red cell count</b> - An example to illustrate the observation of a red cell count for a blood specimen.<br/>
{{pagelink:Example-UKCore-Observation-Lab-RedCellCount}}<br><br>
<b>White cell count</b> - An example to illustrate the observation of a white cell count for a blood specimen.<br/>
{{pagelink:Example-UKCore-Observation-Lab-WhiteCellCount}}
</div>
</nocheck>

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core Observation profile:

- Query and retrieve a patient's laboratory observations
- Record or update a patient's laboratory observations

<br>
The Observation-Lab profile is for individual laboratory tests (Observation-Lab) which may form a larger set of tests, for example a urea and electrolyte test that contains many sub tests, or as a single test, for example Serum ferritin level.
<br><br>
The workflow below shows a possible way to group a set of related laboratory observations into the derived {{pagelink:Profile-Observation-Group-67431}}, which is then referenced within a diagnostic report. Seperate laboratory observations MAY be directly referenced within the diagnostic report.
<br>

{{render: Derived-Profiles-Lab-Example }}{: .img-responsive }

<br>
Depending upon the countries or trusts workflow, an alternative is to have any separate laboratory observations referenced in a {{pagelink:Profile-Observation-Group-67431}} before being referenced in the diagnostic report. Although this creates extra resources it standardises the workflow. 

{{render:Derived-Profiles-Lab-Example-Extra-Group}}{: .img-responsive }

---

## Profile Specific Implementation Guidance: ##

### Mandatory and Must Support Data Elements

The following elements are identified as MustSupport, and it is expected that consumers and suppliers SHALL support these as per the {{pagelink:Guidance-MustSupport-25267}}.

<table class="assets" title="MustSupport element list">
<tr>
<th class="width30">Element</th>
<th class="width70">Reason</th>
</tr>
<tr>
<td><code>Observation.status</code></td>
<td>The status of the result value.</td>
</tr>
<tr>
<td><code>Observation.category</code></td>
<td>A code that classifies the general type of observation being made.</td>
</tr>
<tr>
<td><code>Observation.code</code></td>
<td>Type of observation (code / type)</td>
</tr>
<tr>
<td><code>Observation.subject</code></td>
<td>Who and/or what the observation is about</td>
</tr>
<tr>
<td><code>Observation.effective[x]</code></td>
<td>Clinically relevant time/time-period for observation</td>
</tr>
<tr>
<td><code>Observation.performer</code></td>
<td>Who is responsible for the observation</td>
</tr>
<tr>
<td><code>Observation.value[x]</code></td>
<td>Actual result.</td>
</tr>
<tr>
<td><code>Observation.component</code></td>
<td>Component / sub results.</td>
</tr>
</table>

---

