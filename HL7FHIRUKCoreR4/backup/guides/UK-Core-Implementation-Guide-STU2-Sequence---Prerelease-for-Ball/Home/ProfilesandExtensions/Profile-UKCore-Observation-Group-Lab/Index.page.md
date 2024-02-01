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

<h3>Minimum Viable Content</h3>

The minimum viable content that all provider and consumer systems SHALL support are the elements within the corresponding {{pagelink: Profile-Observation-67521}} table, along with the following.

<table class="assets">
<tr>
<th width="30%">Element</th>
<th width="70%">Reason</th>
</tr>
<tr>
<td><code><s>Observation.value[x]</s></code></td>
<td>Unlike the Observation profile, this derived profile it is not expected to use the <code>Observation.value[x]</code> element.</td>
</tr>
<tr>
<td><code>Observation.hasMember</code></td>
<td>Related resource that belongs to the Observation group</td>
</tr>
<table>

---
