---
topic: Profile-EpisodeOfCare
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-EpisodeOfCare
---
# StructureDefinition-UKCore-EpisodeOfCare

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'UKCoreEpisodeOfCare'
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
	name = 'UKCoreEpisodeOfCare'
select
	Profile_Purpose: purpose
```

<nocheck>
{{page:Home/ProfilesandExtensions/ProfileTemplate.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>Smoking Cessation Therapy</b> -An example to illustrate an episode of care for smoking cessation therapy.<br/>
{{pagelink:Example-UKCore-EpisodeOfCare-SmokingCessationTherapy}}
</div>

<div id="Usage" class="tabcontent">
  <h3>Usage</h3>
  This Profile has the following derived profiles:<br>
<span id="usage">
@```
  from
	StructureDefinition
select id,baseDefinition,status
  where baseDefinition = 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-EpisodeOfCare'
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
	where targetProfile contains 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-EpisodeOfCare'
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
	where targetProfile contains 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-EpisodeOfCare'
```
</span>
</div>

<div id="Feedback" class="tabcontent">
  <h3>Feedback</h3>
Click here to <a href="https://simplifier.net/HL7FHIRUKCoreR4/UKCore-EpisodeOfCare/~issues?level=File">Report Issue for UKCore-EpisodeOfCare</a>.
</div>
</nocheck>

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core EpisodeOfCare profile:

- Query for information about an episode of care associated with a patient
- Record or update information about an episode of care for a patient

<hr class="thickline">

## Profile Specific Implementation Guidance: ##


### Minimum Viable Content

A minimum viable content that all provider and consumer systems SHALL support are the following elements.

<table class="assets" title="Minimum Viable Content list">
<tr>
<th class="width30">Element</th>
<th class="width70">Reason</th>
</tr>
<tr>
<td><code>EpisodeOfCare.patient</code></td>
<td>The patient who is the focus of this episode of care.</td>
</tr>
<tr>
<td><code>EpisodeOfCare.period</code></td>
<td>The interval during which the managing organization assumes the defined responsibility.</td>
</tr>
<tr>
<td><code>EpisodeOfCare.careManager</code></td>
<td>The practitioner that is the care manager/care coordinator for this patient.</td>
</tr>
</table>

<hr class="thickline">