---
topic: Profile-Observation-EarlyWarningTotalScore
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation-EarlyWarningTotalScore
---

# StructureDefinition-UKCore-Observation-EarlyWarningTotalScore

<div id="newAsset" markdown="span" class="alert alert-success" role="alert"><h4><i class="fa fa-star"></i> Important</h4>

This Profile underwent Clinical and Technical Assurance during Sprint 7. This is a new Profile added to UK Core and should undergo review during the Sprint 7 review window.

Click here to <a href="https://simplifier.net/HL7FHIRUKCoreR4/UKCore-Observation-EarlyWarningTotalScore/~issues?level=File">Report Issue for UKCore-Observation-EarlyWarningTotalScore</a>.
</div>

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'UKCoreObservationEarlyWarningTotalScore'
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
	name = 'UKCoreObservationEarlyWarningTotalScore'
select
	Profile_Purpose: purpose
```

<nocheck>
{{page:Home/ProfilesandExtensions/ProfileTemplate.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
<b>NEWS2 Bundle</b> - An example to illustrate a full bundle of National Early Warning Score (NEWS) 2 observations, sub scores, and total score.<br/>
{{pagelink:Example-UKCore-Bundle-NEWS2Observations}}<br><br>
<b>NPEWS Total</b> - An example to illustrate a National Paediatric Early Warning System (NPEWS) total score.<br/>
{{pagelink:Example-UKCore-Observation-NPEWSTotal}}<br><br>
</div>

<div id="Usage" class="tabcontent">
  <h3>Usage</h3>
  This Profile has the following derived profiles:<br>
<span id="usage">
@```
  from
	StructureDefinition
select id,baseDefinition,status
  where baseDefinition = 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation-EarlyWarningTotalScore'
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
	where targetProfile contains 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation-EarlyWarningTotalScore'
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
	where targetProfile contains 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation-EarlyWarningTotalScore'
```
</span>
</div>

<div id="Feedback" class="tabcontent">
  <h3>Feedback</h3>
Click here to <a href="https://simplifier.net/HL7FHIRUKCoreR4/UKCore-Observation-EarlyWarningTotalScore/~issues?level=File">Report Issue for UKCore-Observation-EarlyWarningTotalScore</a>.
</div>
</nocheck>

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core Observation Early Warning Total Score profile:

- Query and retrieve a patient's Early Warning Score
- Record or update a patient's Early Warning Score


<hr class="thickline">

## Profile Specific Implementation Guidance: ##

This is a derived profile of {{pagelink:Profile-Observation,text:UKCore-Observation}} and this page only shows the differences between the two. Refer to the base Profile for more implementation guidance.

### Minimum Viable Content

The minimum viable content that all provider and consumer systems SHALL support are the elements within the corresponding {{pagelink:Profile-Observation,text:UKCore-Observation}} table, along with the following.

<table class="assets" title="Minimum Viable Content list">
<tr>
<th class="width30">Element</th>
<th class="width70">Reason</th>
</tr>
<tr>
<td><code>Observation.status</code></td>
<td>A status of <code>final</code> SHALL be present.</td>
</tr>
<tr>
<td><code>Observation.category</code></td>
<td>A category of <code>survey</code> SHALL be present.</td>
</tr>
<tr>
<td><code>Observation.code</code></td>
<td>A SNOMED CT concept SHALL be present.</td>
</tr>
<tr>
<td><code>Observation.subject</code></td>
<td>A UKCore-Patient SHALL be present.</td>
</tr>
<tr>
<td><code>Observation.effective[x]</code></td>
<td>An effective time or date SHALL be present.</td>
</tr>
<tr>
<td><code>Observation.value[x]</code></td>
<td>A quantity SHALL be present.</td>
</tr>
<tr>
<td><code>Observation.derivedFrom</code></td>
<td>References to the observations from which the component scores are derived SHOULD be present.</td>
</tr>
<tr>
<td><code>Observation.component</code></td>
<td>Components representing the codes and sub scores SHOULD be present.</td>
</tr>
</table>

---