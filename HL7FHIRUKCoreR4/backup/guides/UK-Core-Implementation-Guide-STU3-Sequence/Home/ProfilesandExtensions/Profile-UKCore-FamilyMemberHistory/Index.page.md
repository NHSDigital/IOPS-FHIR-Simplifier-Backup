---
topic: Profile-FamilyMemberHistory
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-FamilyMemberHistory
usage: http://hl7.org/fhir/StructureDefinition/FamilyMemberHistory
issue: UKCore-FamilyMemberHistory
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
</nocheck>


<div id="ProfileGuidance">

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core FamilyMemberHistory profile:
- Query for details of a FamilyMemberHistory
- Exchange FamilyMemberHistory information within a FHIR document or message.

<hr class="thickline">

## Profile Specific Implementation Guidance: ##

### Mandatory and Must Support Data Elements

The following elements are identified as MustSupport, and it is expected that consumers and suppliers SHALL support these as per the {{pagelink:Guidance-MustSupport}}.

<table class="assets" title="MustSupport element list">
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
</div>

---
