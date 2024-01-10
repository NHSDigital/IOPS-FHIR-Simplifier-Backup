---
topic: Profile-FamilyMemberHistory
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-FamilyMemberHistory
---
# StructureDefinition-UKCore-FamilyMemberHistory

<nocheck>
{{page:Home/ProfilesandExtensions/ProfileTemplate.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>Associated Encounter</b> - An example to illustrate using the extension to indicate the encounter for which the family members condition was recorded.<br>
{{pagelink:Example-UKCore-Extension-AssociatedEncounter}}
  <br><br>
  <b>Father with Diabetes</b> - An example to illustrate the the use of FamilyMemberHistory to record a father with diabetes.
  <br>{{pagelink:Example-UKCore-FamilyMemberHistory-FatherDiabetes}}
  <br><br>
  <b>Participant Reference</b> - An example to illustrate the pre-adopted R5 element via an extension, which is used to indicate the performer of the family member history related activity.<br>
  {{pagelink:Example-UKCore-Extension-Participant}}
</div>

<div id="Usage" class="tabcontent">
  <h3>Usage</h3>
  This Profile has the following derived profiles:<br>
<span id="usage">
@```
  from
	StructureDefinition
select id,baseDefinition,status
  where baseDefinition = 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-FamilyMemberHistory'
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
	where targetProfile contains 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-FamilyMemberHistory'
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
	where targetProfile contains 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-FamilyMemberHistory'
```
</span>
</div>

<div id="Feedback" class="tabcontent">
  <h3>Feedback</h3>
Click here to <a href="https://simplifier.net/HL7FHIRUKCoreR4/UKCore-FamilyMemberHistory/~issues?level=File">Report Issue for UKCore-FamilyMemberHistory</a>.
</div>
</nocheck>

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core FamilyMemberHistory profile:
- Query for details of a FamilyMemberHistory
- Exchange FamilyMemberHistory information within a FHIR document or message.

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
<td><code>FamilyMemberHistory.status</code></td>
<td>A code specifying the status of the record of the family history of a specific family member.
</td>
</tr>
<tr>
<td><code>FamilyMemberHistory.patient</code></td>
<td>The person who this history concerns.
</td>
</tr>
<tr>
<td><code>FamilyMemberHistory.date</code></td>
<td>The date (and possibly time) when the family member history was recorded or last updated.
</td>
</tr>
<tr>
<td><code>FamilyMemberHistory.name</code></td>
<td>Allows greater ease in ensuring the same person is being talked about.
</td>
</tr>
<tr>
<td><code>FamilyMemberHistory.relationship</code></td>
<td>Relationship to the subject.</td>
</tr>
<tr>
<td><code>FamilyMemberHistory.condition</code></td>
<td>Condition that the related person had.</td>
</tr>
</table>

---
