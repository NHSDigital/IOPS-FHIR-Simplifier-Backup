---
subject: https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-AdmissionMethod
---
## StructureDefinition Extension-UKCore-BirthSex

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'ExtensionUKCoreBirthSex'
select
	Canonical_URL: url,
	Description: description,
	Profile_Purpose: purpose
```

<table id="addToTranspose">
<tr><td>Context of Use</td>
<td>{{pagelink:Profile-Patient,text:Patient}}</td>
</tr>
</table>

</div>
<br>

{{page:Home/ProfilesandExtensions/ExtensionTemplate.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>Birth Sex</b>- An example to illustrate the extension for a patient's birth sex.<br>
  {{pagelink:Example-UKCore-Extension-BirthSex}}
  <br><br>
</div>

<h3 id="guidance-birthsex">Extension Specific Guidance</h3>
There is a binding within this extension to a {{pagelink:ValueSet-UKCore-BirthSex}}.

---
