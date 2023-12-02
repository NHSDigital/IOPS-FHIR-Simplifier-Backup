---
topic: Profile-Location-14324
---
# StructureDefinition-UKCore-Location

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'UKCoreLocation'
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
	name = 'UKCoreLocation'
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
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Location, snapshot}}
</div>

<div id="Differential View" class="tabcontent">
  <h3>Differential View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Location, diff}}
</div>

<div id="Hybrid View" class="tabcontent">
  <h3>Hybrid View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Location, hybrid}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Location, snapshot}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Location, snapshot}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Location, snapshot}}
</div>

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>SJUH Location</b> -  An example to illustrate a Cardiology department in a hospital<br/>
{{pagelink:Example-UKCore-Location-CardiologySJUH}}
 <br><br>
 <b>General Practice Nurse Clinic location</b> - An example to illustrate a General Practice Nurse Clinic<br/>
 {{pagelink:Example-UKCore-Location-GeneralPracticeNurseClinic}}
</div>
</nocheck>

### Example Usage Scenarios ###
The following are example usage scenarios for the UKCore Location profile:

- To describe care locations such as hospital wards
- To describe locations where patient care has or may take place, including scenes of accidents like by the side of a road.

---

## Profile Specific Implementation Guidance: ##

<h3>Minimum Viable Content</h3>

A minimum viable content that all provider and consumer systems SHALL support are the following elements.

<table class="assets">
<tr>
<th width="30%">Element</th>
<th width="70%">Reason</th>
</tr>
<tr>
<td><code>Location.identifier:odsSiteCode</code></td>
<td>ODS Site code to identify the organisation at site level.</td>
</tr>
<tr>
<td><code>Location.status</code></td>
<td>Is the location active, inactive, or suspended</td>
</tr>
<tr>
<td><code>Location.name</code></td>
<td>Name of the location as used by humans. This does not need to be unique.</td>
</tr>
<tr>
<td><code>Location.address</code></td>
<td>If locations can be visited, we need to keep track of their address.</td>
</tr>
</table>

---
