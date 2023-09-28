---
topic: Profile-FamilyMemberHistory-69978
---
# StructureDefinition-UKCore-FamilyMemberHistory

<div id="newAsset" markdown="span" class="alert alert-success" role="alert"><h4><i class="fa fa-star"></i> Important</h4>

This Profile underwent Clinical and Technical Assurance during Sprint 6. This is a new Profile added to UK Core and should undergo review in this STU2 ballot.
</div>

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'UKCoreFamilyMemberHistory'
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
	name = 'UKCoreFamilyMemberHistory'
select
	Profile_Purpose: purpose
```

<nocheck>
<div class="tab fhirTree">
 <button class="tablinks active" onclick="openTab(event, 'Snapshot View')">Snapshot View</button>
  <button class="tablinks" onclick="openTab(event, 'Differential View')">Differential View</button>
  <button class="tablinks" onclick="openTab(event, 'Hybrid View')">Hybrid View</button>
   <button class="tablinks" onclick="openTab(event, 'Table View')">Table View</button>
   <button class="tablinks" onclick="openTab(event, 'XML View')">XML View</button>
  <button class="tablinks" onclick="openTab(event, 'JSON View')">JSON View</button>
  <button class="tablinks" onclick="openTab(event, 'Examples')">Examples</button>
</div>

<div id="Snapshot View" class="tabcontent" style="display:block">
  <h3>Snapshot View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-FamilyMemberHistory, snapshot}}
</div>

<div id="Differential View" class="tabcontent">
  <h3>Differential View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-FamilyMemberHistory, diff}}
</div>

<div id="Hybrid View" class="tabcontent">
  <h3>Hybrid View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-FamilyMemberHistory, hybrid}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.hl7.org.uk/StructureDefinition/UKCore-FamilyMemberHistory, snapshot}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:https://fhir.hl7.org.uk/StructureDefinition/UKCore-FamilyMemberHistory, snapshot}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:https://fhir.hl7.org.uk/StructureDefinition/UKCore-FamilyMemberHistory, snapshot}}
</div>

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>Associated Encounter</b> - An example to illustrate using the extension to indicate the encounter for which the family members condition was recorded.<br>
{{pagelink:Example-UKCore-FamilyMemberHistory-Extension-AssociatedEncounter}}
  <br><br>
  <b>Father with Diabetes</b> - An example to illustrate the the use of FamilyMemberHistory to record a father with diabetes.
  <br>{{pagelink:Example-UKCore-FamilyMemberHistory-FatherDiabetes}}
  <br><br>
  <b>Participant Reference</b> - An example to illustrate the pre-adopted R5 element via an extension, which is used to indicate the performer of the family member history related activity.<br>
  {{pagelink:Example-UKCore-FamilyMemberHistory-Extension-Participant}}
</div>
</nocheck>

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core FamilyMemberHistory profile:
- Query for details of a FamilyMemberHistory
- Exchange FamilyMemberHistory information within a FHIR document or message.

---

## Profile Specific Implementation Guidance: ##

### Minimum Viable Content

A minimum viable content that all provider and consumer systems SHALL support are the following elements.

<table class="assets">
<tr>
<th width="30%">Element</th>
<th width="70%">Reason</th>
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
<td><code>FamilyMemberHistory.sex</code></td>
<td>The birth sex of the family member.
</td>
</tr>
<tr>
<td><code>FamilyMemberHistory.condition</code></td>
<td>Condition that the related person had.</td>
</tr>
</table>

---
