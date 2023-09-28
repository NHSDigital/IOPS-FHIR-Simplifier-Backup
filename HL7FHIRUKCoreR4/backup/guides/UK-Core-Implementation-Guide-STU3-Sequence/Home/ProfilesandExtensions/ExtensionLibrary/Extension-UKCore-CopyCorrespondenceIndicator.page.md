---
subject: https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-CopyCorrespondenceIndicator
---
## StructureDefinition Extension-UKCore-CopyCorrespondenceIndicator

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'ExtensionUKCoreCopyCorrespondenceIndicator'
select
	Canonical_URL: url,
	Description: description,
	Profile_Purpose: purpose
```
</div>
<br>

<table id="addToTranspose">
<tr><td>Context of Use</td>
<td>{{pagelink:Profile-RelatedPerson,text:RelatedPerson}}<br/>
{{pagelink:Profile-Patient,text:Patient.contact}}</td>
</tr>
</table>

{{page:Home/ProfilesandExtensions/ExtensionTemplate.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>Copy Correspondence Indicator</b>- This shows the extension that uses a Boolean value of true to indicate that the person named should be sent a copy of the correspondence.<br>
{{pagelink:Example-UKCore-Extension-CopyCorrespondenceIndicator}}
<br><br>
</div>

---
