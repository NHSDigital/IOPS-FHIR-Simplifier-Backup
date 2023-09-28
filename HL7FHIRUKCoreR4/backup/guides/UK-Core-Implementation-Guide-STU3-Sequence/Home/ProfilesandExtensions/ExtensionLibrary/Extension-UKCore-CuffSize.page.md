---
subject: https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-CuffSize
---
## StructureDefinition Extension-UKCore-CuffSize

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'ExtensionUKCoreCuffSize'
select
	Canonical_URL: url,
	Description: description,
	Profile_Purpose: purpose
```
</div>
<br>

<table id="addToTranspose">
<tr><td>Context of Use</td>
<td>{{pagelink:Profile-Device-BloodPressure,text:Device}}</td>
</tr>
</table>

{{page:Home/ProfilesandExtensions/ExtensionTemplate.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>Cuff Size</b> - An example to illustrate a blood pressure monitoring device with a large cuff.<br>
{{pagelink:Example-UKCore-Extension-CuffSize}}
<br><br>
</div>

<h3 id="guidance-cuffsize">Extension Specific Guidance</h3>
There is a binding within this extension to a {{pagelink:ValueSet-UKCore-BloodPressure-CuffSize}}.

---
