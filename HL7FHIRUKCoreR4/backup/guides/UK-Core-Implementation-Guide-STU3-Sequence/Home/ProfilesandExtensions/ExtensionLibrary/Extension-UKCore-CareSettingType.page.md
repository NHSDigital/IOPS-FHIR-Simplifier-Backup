---
subject: https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-CareSettingType
---
## StructureDefinition Extension-UKCore-CareSettingType

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'ExtensionUKCoreCareSettingType'
select
	Canonical_URL: url,
	Description: description,
	Profile_Purpose: purpose
```

<table id="addToTranspose">
<tr><td>Context of Use</td>
<td>{{pagelink:Profile-Composition,text:Composition}} <br/> 
{{pagelink:Profile-List,text:List}}</td>
</tr>
</table>

</div>
<br>

{{page:Home/ProfilesandExtensions/ExtensionTemplate.page.md}}

<div id="Examples" class="tabcontent">

  <h3>Examples</h3>
  <b>Care Setting Type</b>- An example to illustrate the care setting of a FHIR document.<br>
{{pagelink:Example-UKCore-Extension-CareSettingType}}
<br><br>
</div>

<h3 id="guidance-caresettingtype">Extension Specific Guidance</h3>
There is a binding within this extension to a {{pagelink:ValueSet-UKCore-CareSettingType}}.

---
