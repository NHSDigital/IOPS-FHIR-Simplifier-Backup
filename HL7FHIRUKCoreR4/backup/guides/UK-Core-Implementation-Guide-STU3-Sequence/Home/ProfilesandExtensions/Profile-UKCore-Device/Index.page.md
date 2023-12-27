---
topic: Profile-Device
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-Device
---

# StructureDefinition-UKCore-Device

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'UKCoreDevice'
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
	name = 'UKCoreDevice'
select
	Profile_Purpose: purpose
```

<nocheck>
{{page:Home/ProfilesandExtensions/ProfileTemplate.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>Colostomy Bag</b> - An example to illustrate a colostomy bag<br/>
{{pagelink:Example-UKCore-Device-ColostomyBag}}
<b>Software as a Medical Device</b> - An example to illustrate recording AI softweare as a medical device.<br/>
{{pagelink:Example-UKCore-Device-SoftwareAsAMedicalDevice}}<br><br>
<b>Sphygmomanometer</b> - An example to illustrate recording a specific blood pressure device.<br/>
{{pagelink:Example-UKCore-Device-Sphygmomanometer}}<br><br>
</div>

<div id="Usage" class="tabcontent">
  <h3>Usage</h3>
  This Profile has the following derived profiles:<br>
<span id="usage">
@```
  from
	StructureDefinition
select id,baseDefinition,status
  where baseDefinition = 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-Device'
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
	where targetProfile contains 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-Device'
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
	where targetProfile contains 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-Device'
```
</span>
</div>

<div id="Feedback" class="tabcontent">
  <h3>Feedback</h3>
Click here to <a href="https://simplifier.net/HL7FHIRUKCoreR4/UKCore-Device/~issues?level=File">Report Issue for UKCore-Device</a>.
</div>
</nocheck>

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core Device profile:

- Query and retrieve information regarding a medical device
- Record or update a device used during a patients care


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
<td><code>Device.status</code></td>
<td>The status of the Device.</td>
</tr>
<tr>
<td><code>Device.type</code></td>
<td>The type of the Device.</td>
</tr>
</table>

---
