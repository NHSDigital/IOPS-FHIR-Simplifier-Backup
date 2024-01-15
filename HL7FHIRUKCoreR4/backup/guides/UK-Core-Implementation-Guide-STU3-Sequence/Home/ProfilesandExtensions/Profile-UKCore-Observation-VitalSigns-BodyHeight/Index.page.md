---
topic: Profile-Observation-VitalSigns-BodyHeight
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation-VitalSigns-BodyHeight
---

# StructureDefinition-UKCore-Observation-VitalSigns-BodyHeight

<div id="newAsset" markdown="span" class="alert alert-success" role="alert"><h4><i class="fa fa-star"></i> Important</h4>

This Profile underwent Clinical and Technical Assurance during Sprint 7. This is a new Profile added to UK Core and should undergo review during the Sprint 7 review window.

Click here to <a href="https://simplifier.net/HL7FHIRUKCoreR4/UKCore-Observation-VitalSigns-BodyHeight/~issues?level=File">Report Issue for UKCore-Observation-VitalSigns-BodyHeight</a>.
</div>

<nocheck>
{{page:Home/ProfilesandExtensions/ProfileTemplate.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
<b>Body Height</b> - An example to illustrate recording a patients height.<br/>
{{pagelink:Example-UKCore-Observation-VitalSigns-BodyHeight}}<br><br>
</div>

<div id="Usage" class="tabcontent">
  <h3>Usage</h3>
  This Profile has the following derived profiles:<br>
<span id="usage">
@```
  from
	StructureDefinition
select id,baseDefinition,status
  where baseDefinition = 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation-VitalSigns-BodyHeight'
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
	where targetProfile contains 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation-VitalSigns-BodyHeight'
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
	where targetProfile contains 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation-VitalSigns-BodyHeight'
```
</span>
</div>

<div id="Feedback" class="tabcontent">
  <h3>Feedback</h3>
Click here to <a href="https://simplifier.net/HL7FHIRUKCoreR4/UKCore-Observation-VitalSigns-BodyHeight/~issues?level=File">Report Issue for UKCore-Observation-VitalSigns-BodyHeight</a>.
</div>
</nocheck>


### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core Observation Vital Signs Body Height profile:

- Query and retrieve a patient's body height
- Record or update a patient's body height

<hr class="thickline">

## Profile Specific Implementation Guidance: ##

The UKCore-Observation-VitalSigns-BodyHeight profile further derives from {{pagelink:Profile-Observation-VitalSigns,text:UKCore-Observation-VitalSigns}} and this page only shows the differences between the two. Refer to {{pagelink:Profile-Observation,text:UKCore-Observation}} and {{pagelink:Profile-Observation-VitalSigns,text:UKCore-Observation-VitalSigns}} for more implementation guidance.

### Minimum Viable Content

The minimum viable content that all provider and consumer systems SHALL support are the elements within the corresponding {{pagelink:Profile-Observation,text:UKCore-Observation}} and {{pagelink:Profile-Observation-VitalSigns,text:UKCore-Observation-VitalSigns}} tables, along with the following.

<table class="assets" title="Minimum Viable Content list">
<tr>
<th class="width30">Element</th>
<th class="width70">Reason</th>
</tr>
<tr>
<td><code>Observation.value[x]</code></td>
<td>A quantity SHALL be present.</td>
</tr>
</table>
