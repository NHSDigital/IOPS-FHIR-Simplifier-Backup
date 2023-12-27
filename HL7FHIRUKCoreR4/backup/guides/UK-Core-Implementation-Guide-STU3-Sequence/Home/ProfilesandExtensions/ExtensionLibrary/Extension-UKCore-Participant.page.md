---
subject: http://hl7.org/fhir/5.0/StructureDefinition/extension-FamilyMemberHistory.participant
---
## StructureDefinition Extension-UKCore-FamilyMemberHistoryParticipant

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'ExtensionUKCoreFamilyMemberHistoryParticipant'
select
	Canonical_URL: url,
  Status: status,
  Current_Version: version,
  Last_Updated: date,
	Description: description,
	Profile_Purpose: purpose
```

<table id="addToTranspose">
<tr><td>Context of Use</td>
<td>{{pagelink:Profile-FamilyMemberHistory,text:FamilyMemberHistory}}</td>
</tr>
</table>

</div>
<br>


{{page:Home/ProfilesandExtensions/ExtensionTemplate.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>Participant Reference</b> - An example to illustrate the pre-adopted R5 element via an extension, which is used to indicate the performer of the family member history related activity.<br>
  {{pagelink:Example-UKCore-Extension-Participant}}
  <br><br>
</div>
<div id="Feedback" class="tabcontent">
  <h3>Feedback</h3>
Click here to <a href="https://simplifier.net/HL7FHIRUKCoreR4/Extension-UKCore-FamilyMemberHistoryParticipant/~issues?level=File">Report Issue for Extension-UKCore-FamilyMemberHistoryParticipant</a>.
</div>


<h3 id="guidance-fmhparticipant">Extension Specific Guidance</h3>
Where possible, it is expected that the resource being referenced SHOULD conform to one of the following UK Core profiles:

- [https://simplifier.net/guide/ukcoreimplementationguideassetsindevelopment/home/profilesandextensions/profileukcore-careteam/index.guide.md?version=current](UKCore-CareTeam)
- {{pagelink:Profile-Device}}
- {{pagelink:Profile-Organization}}
- {{pagelink:Profile-Patient}}
- {{pagelink:Profile-Practitioner}}
- {{pagelink:Profile-PractitionerRole}}
- {{pagelink:Profile-RelatedPerson}}


---