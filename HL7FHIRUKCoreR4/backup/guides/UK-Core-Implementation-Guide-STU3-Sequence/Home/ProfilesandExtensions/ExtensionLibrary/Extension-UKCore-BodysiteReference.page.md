---
subject: https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-BodySiteReference
---
## StructureDefinition Extension-UKCore-BodySiteReference

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'ExtensionUKCoreBodySiteReference'
select
	Canonical_URL: url,
	Description: description,
	Profile_Purpose: purpose
```
</div>
<br>

<table id="addToTranspose">
<tr><td>Context of Use</td>
<td>{{pagelink:Profile-Specimen,text:Specimen.collection.bodySite}}</td>
</tr>
</table>

{{page:Home/ProfilesandExtensions/ExtensionTemplate.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>Median Cubital Vein</b>- An example to illustrate the extension for a referenced body site.<br>
  {{pagelink:Example-UKCore-Extension-BodySiteReference}}
  <br><br>
</div>


---
