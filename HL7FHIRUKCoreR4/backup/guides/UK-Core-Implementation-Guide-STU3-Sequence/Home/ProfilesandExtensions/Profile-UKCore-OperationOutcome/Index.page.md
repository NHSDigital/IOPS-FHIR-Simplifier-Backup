---
topic: Profile-OperationOutcome
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-OperationOutcome
---
# StructureDefinition-UKCore-OperationOutcome

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'UKCoreOperationOutcome'
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
	name = 'UKCoreOperationOutcome'
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
<b>DateError</b> - An example to illustrate an error returned due to an error in a date.
<br>{{pagelink:Example-UKCore-OperationOutcome-DateError}}
</div>

<div id="Usage" class="tabcontent">
  <h3>Usage</h3>
  This Profile has the following derived profiles:<br>
<span id="usage">
@```
  from
	StructureDefinition
select id,baseDefinition,status
  where baseDefinition = 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-OperaitonOutcome'
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
	where targetProfile contains 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-OperaitonOutcome'
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
	where targetProfile contains 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-OperaitonOutcome'
```
</span>
</div>
</nocheck>

<hr class="thickline">

## Profile Specific Implementation Guidance: ##


<h3>Minimum Viable Content</h3>

A minimum viable content that all provider and consumer systems SHALL support are the following elements.

<table class="assets" title="Minimum Viable Content list">
<tr>
<th class="width30">Element</th>
<th class="width70">Reason</th>
</tr>
<tr>
<td><code>OperationOutcome.issue</code></td>
<td>A single issue associated with the action</td>
</tr>
<tr>
<td><code>OperationOutcome.issue.severity</code></td>
<td>Indicates how relevant the issue is to the overall success of the action. This is labelled as "Is Modifier" because applications should not confuse hints and warnings with errors.</td>
</tr>
<tr>
<td><code>OperationOutcome.issue.code</code></td>
<td>Error or warning code</td>
</tr>
<tr>
<td><code>OperationOutcome.issue.expression</code></td>
<td>FHIRPath of element(s) related to issue</td>
</tr>
</table>

---
