---
topic: Profile-MessageHeader
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-MessageHeader
---
# StructureDefinition-UKCore-MessageHeader


<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'UKCoreMessageHeader'
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
	name = 'UKCoreMessageHeader'
select
	Profile_Purpose: purpose
```

<nocheck>
{{page:Home/ProfilesandExtensions/ProfileTemplate.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
<b>Discharge Summary</b> - An example to illustrate a message header for a discharge summary<br>
{{pagelink:Example-UKCore-MessageHeader-Discharge}}
<br><br>
<b>Extension-ResponseRequest</b> - An example to illustrate the HL7 extension ResponseRequest.<br>
{{pagelink:Example-UKCore-Extension-ResponseRequest}}
</div>

<div id="Usage" class="tabcontent">
  <h3>Usage</h3>
  This Profile has the following derived profiles:<br>
<span id="usage">
@```
  from
	StructureDefinition
select id,baseDefinition,status
  where baseDefinition = 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-MessageHeader'
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
	where targetProfile contains 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-MessageHeader'
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
	where targetProfile contains 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-MessageHeader'
```
</span>
</div>

<div id="Feedback" class="tabcontent">
  <h3>Feedback</h3>
Click here to <a href="https://simplifier.net/HL7FHIRUKCoreR4/UKCore-MessageHeader/~issues?level=File">Report Issue for UKCore-MessageHeader</a>.
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
<td><code>MessageHeader.event[x]</code></td>
<td>Code for the event this message represents or link to event definition</td>
</tr>
<tr>
<td><code>MessageHeader.destination</code></td>
<td>The destination application which the message is intended for.
</td>
</tr>
<tr>
<td><code>MessageHeader.sender</code></td>
<td>Real world sender of the message</td>
</tr>
<tr>
<td><code>MessageHeader.source</code></td>
<td>The source application from which this message originated.
</td>
</tr>
<tr>
<td><code>MessageHeader.focus</code></td>
<td>The actual content of the message</td>
</tr>
</table>

---
