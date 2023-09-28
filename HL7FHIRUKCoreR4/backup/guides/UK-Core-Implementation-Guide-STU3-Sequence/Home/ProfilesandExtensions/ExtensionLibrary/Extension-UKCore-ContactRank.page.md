---
subject: https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-ContactRank
---
## StructureDefinition Extension-UKCore-ContactRank

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'ExtensionUKCoreContactRank'
select
	Canonical_URL: url,
	Description: description,
	Profile_Purpose: purpose
```
</div>
<br>

<table id="addToTranspose">
<tr><td>Context of Use</td>
<td>{{pagelink:Profile-Patient,text:Patient.contact}}</td>
</tr>
</table>

{{page:Home/ProfilesandExtensions/ExtensionTemplate.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>Contact Rank</b>- This example shows the extension which uses a PositiveInt to indicate the order that the people listed as contacts for the patient should be contacted. This example uses the value 1 to show that this is the first person who should be contacted.<br>
{{pagelink:Example-UKCore-Extension-ContactRank}}
<br><br>
</div>

---