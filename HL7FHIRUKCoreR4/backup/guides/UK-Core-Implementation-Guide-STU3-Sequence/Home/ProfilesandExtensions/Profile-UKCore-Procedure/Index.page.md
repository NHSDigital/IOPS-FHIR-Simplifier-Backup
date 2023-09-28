---
topic: Profile-Procedure
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-Procedure
expand: 2
---

# StructureDefinition-UKCore-Procedure

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'UKCoreProcedure'
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
	name = 'UKCoreProcedure'
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

<div id="Tree View" class="tabcontent" style="display:block">
{{tree, buttons}}
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
  <b>Skin Examination</b>- An example to illustrate a procedure of skin examination.<br>
{{pagelink:Example-UKCore-Procedure-ExaminationOfSkin}}
</div>

<div id="Usage" class="tabcontent">
  <h3>Usage</h3>
  This Profile has the following derived profiles:<br>
<span id="usage">
@```
  from
	StructureDefinition
select id,baseDefinition,status
  where baseDefinition = 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-Procedure'
  and status = 'active'
```
</span>
<br><br>
  This Profile is referenced in the following Extensions: <br>
<span id="usage">
@```
from
	StructureDefinition
  where type='Extension' and status = 'active'
 select id,
	for differential.element
	select
	join type {targetProfile}
	where targetProfile contains 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-Procedure'
```
</span>
<br><br>
  This Profile is referenced in the following Profiles: <br>
<span id="usage">
@```
from
	StructureDefinition
  where type !='Extension' and status = 'active'
 select id,
	for differential.element
	select
	join type {targetProfile}
	where targetProfile contains 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-Procedure'
```
</span>
</div>
</nocheck>

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core Procedure profile:

- Query for procedures performed on a Patient
- Record or update a procedure performed on a Patient

<hr class="thickline">

## Profile specific implementation guidance: ##


<h3>Minimum Viable Content</h3>

A minimum viable content that all provider and consumer systems SHALL support are the following elements.

<table class="assets" title="Minimum Viable Content list">
<tr>
<th class="width30">Element</th>
<th class="width70">Reason</th>
</tr>
<tr>
<td><code>Procedure.status</code></td>
<td>A code specifying the state of the procedure.</td>
</tr>
<tr>
<td><code>Procedure.code</code></td>
<td>A code specifying the state of the procedure.</td>
</tr>
<tr>
<td><code>Procedure.subject</code></td>
<td>Who the procedure was performed on.</td>
</tr>
<tr>
<td><code>Procedure.performed[x]</code></td>
<td>When the procedure was performed.</td>
</tr>
<tr>
<td><code>Procedure.performedDateTime</code></td>
<td>Date and time the procedure was performed.</td>
</tr>
</table>

---