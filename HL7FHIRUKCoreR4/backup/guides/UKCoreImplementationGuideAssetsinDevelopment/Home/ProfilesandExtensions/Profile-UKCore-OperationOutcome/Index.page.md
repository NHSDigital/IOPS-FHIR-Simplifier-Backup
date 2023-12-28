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
  Status: status,
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
{{page:Home/ProfilesandExtensions/ProfileTemplate.page.md}}

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
  where baseDefinition = 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-OperationOutcome'
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
	where targetProfile contains 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-OperationOutcome'
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
	where targetProfile contains 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-OperationOutcome'
```
</span>
</div>

<div id="Feedback" class="tabcontent">
  <h3>Feedback</h3>
Click here to <a href="https://simplifier.net/HL7FHIRUKCoreR4/UKCore-OperationOutcome/~issues?level=File">Report Issue for UKCore-OperationOutcome</a>.
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
