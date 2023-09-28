---
subject: https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-EthnicCategory
---
## StructureDefinition Extension-UKCore-EthnicCategory

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'ExtensionUKCoreEthnicCategory'
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
<b>Ethnic Category</b> - An example to illustrate patient Ethnic Category information. </br>
{{pagelink:Example-UKCore-Extension-EthnicCategory}}
<br><br>
</div>

<h3 id="guidance-ethniccategory">Extension Specific Guidance</h3>
There is a binding within this extension to a {{pagelink:ValueSet-UKCore-EthnicCategory}}.

---
