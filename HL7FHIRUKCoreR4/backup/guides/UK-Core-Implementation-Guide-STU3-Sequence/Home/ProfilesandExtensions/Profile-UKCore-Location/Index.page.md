---
topic: Profile-Location
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-Location
expand: 2
---
# StructureDefinition-UKCore-Location

<nocheck>
{{page:Home/ProfilesandExtensions/ProfileTemplate.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>SJUH Location</b> -  An example to illustrate a Cardiology department in a hospital<br/>
{{pagelink:Example-UKCore-Location-CardiologySJUH}}
 <br><br>
 <b>General Practice Nurse Clinic location</b> - An example to illustrate a General Practice Nurse Clinic<br/>
 {{pagelink:Example-UKCore-Location-GeneralPracticeNurseClinic}}
</div>

<div id="Usage" class="tabcontent">
  <h3>Usage</h3>
  This Profile has the following derived profiles:<br>
<span id="usage">
@```
  from
	StructureDefinition
select id,baseDefinition,status
  where baseDefinition = 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-Location'
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
	where targetProfile contains 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-Location'
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
	where targetProfile contains 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-Location'
```
</span>
</div>

<div id="Feedback" class="tabcontent">
  <h3>Feedback</h3>
Click here to <a href="https://simplifier.net/HL7FHIRUKCoreR4/UKCore-Location/~issues?level=File">Report Issue for UKCore-Location</a>.
</div>
</nocheck>

### Example Usage Scenarios ###
The following are example usage scenarios for the UKCore Location profile:

- To describe care locations such as hospital wards
- To describe locations where patient care has or may take place, including scenes of accidents like by the side of a road.

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

<hr class="thickline">
