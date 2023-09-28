---
subject: https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-DeathNotificationStatus
---
## StructureDefinition Extension-UKCore-DeathNotificationStatus

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'ExtensionUKCoreDeathNotificationStatus'
select
	Canonical_URL: url,
	Description: description,
	Profile_Purpose: purpose
```
</div>
<br>

<table id="addToTranspose">
<tr><td>Context of Use</td>
<td>{{pagelink:Profile-Patient,text:Patient}}</td>
</tr>
</table>

{{page:Home/ProfilesandExtensions/ExtensionTemplate.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>Death notification Status</b>- An example to illustrate the extension to indicate the death notification status of the patient.<br>
{{pagelink:Example-UKCore-Extension-DeathNotificationStatus}}
<br><br>
</div>

<h3 id="guidance-deathnotificationstatus">Extension Specific Guidance</h3>
There is a binding within this extension, `deathNotificationStatus` element to a {{pagelink:ValueSet-UKCore-DeathNotificationStatus}}.

---

