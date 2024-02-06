---
topic: Profile-Observation-Group-67431
---

# StructureDefinition-UKCore-Observation-Group-Lab

<div markdown="span" class="alert alert-warning" role="alert"><h4><i class="fa fa-warning"></i> Breaking Change</h4>
The <code>id</code> / <code>title</code> / <code>name</code> / <code>url</code> of this profile were changed in this release, as a result of the UK Core STU2 Sequence ballot reconciliation actions.
</div>

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'UKCoreObservationGroupLab'
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
	name = 'UKCoreObservationLabGroup'
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
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation-Group-Lab, snapshot}}
</div>

<div id="Differential View" class="tabcontent">
  <h3>Differential View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation-Group-Lab, diff}}
</div>

<div id="Hybrid View" class="tabcontent">
  <h3>Hybrid View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation-Group-Lab, hybrid}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation-Group-Lab, snapshot}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation-Group-Lab, snapshot}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation-Group-Lab, snapshot}}
</div>

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
<b>Full Blood count</b> - An example to illustrate a full blood count using multiple lab observation references.<br/>
{{pagelink:Example-UKCore-Observation-Group-FullBloodCount}}
</div>
</nocheck>

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core Observation profile:

- Group specific laboratory observations together, for example Full Blood Count,
- Place laboratory observations in an ordered fashion.
<br><br>
The Observation-Group-Lab profile is used to reference multiple individual laboratory observations (Observation-Lab) which together form a larger test set, for example a urea and electrolytes test that contains many several sub tests. 
<br><br>
{{render: Derived-Profiles-Lab-Example }}{: .img-responsive }
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
<td><code>Observation.hasMember</code></td>
<td>Related resource that belongs to the Observation group</td>
</tr>
<tr>
<td><code>Observation.component</code></td>
<td>Component / sub results.</td>
</tr>
</table>

---
